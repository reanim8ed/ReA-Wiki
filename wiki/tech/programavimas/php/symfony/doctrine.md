# Doctrine

## Entity changeset

`Doctrine` offers very powerful API for getting entity properties that have changed. This can be achieved using `Doctrine\ORM\UnitOfWork`. We can call:

* `Doctrine\ORM\UnitOfWork::computeChangeSets()` to compute all the changes that have been done to entities and collections and store these changes;
* `Doctrine\ORM\UnitOfWork::getEntityChangeSet($entity)` to retrieve all changes to our entity object;
* `Doctrine\ORM\UnitOfWork::getOriginalEntityData($entity)` to retrieve the original data of an entity before introduced changes.

This simple example will explain it:

```php
// find entity
$post = $em->find('Entity\Post', 1);
// change property value
$post->setStatus(\Entity\Post::STATUS_PUBLISHED);

$uow = $em->getUnitOfWork();
// this step is required only if you are using UnitOfWork outside of listeners
$uow->computeChangeSets();
$changeset = $uow->getEntityChangeSet($post);
```

But what about relations? While working with `Doctrine2` relations we are dealing with `Doctrine\ORM\PersistentCollection` which also has some useful public methods:

* `Doctrine\ORM\PersistentCollection::getSnapshot` to return the last snapshot of the elements in the collection;
* `Doctrine\ORM\PersistentCollection::getDeleteDiff` to return removed entities from the collection;
* `Doctrine\ORM\PersistentCollection::getInsertDiff` to return new entities thast have been added to the collection;
* `Doctrine\ORM\PersistentCollection::isDirty` to check whether this collection is dirty which means its state needs to be synchronized with the database.

Those methods are marked in doc as `INTERNAL` but have public access.

Usage:

```php
// find entity
$post = $em->find('Entity\Post', 1);
$tag1 = $em->find('Entity\Tag', 1);
$tag2 = $em->find('Entity\Tag', 2);
 
$uow = $em->getUnitOfWork();
 
$post->addTag($tag1);
// this step is required only if you are using UnitOfWork outside of listeners
$uow->computeChangeSets();
// entities that have been added
$changeset = $post->getTags()->getInsertDiff();
 
$post->removeTag($tag2);
// this step is required only if you are using UnitOfWork outside of listeners
$uow->computeChangeSets();
// entities that have been removed
$changeset = $post->getTags()->getDeleteDiff();
```

Another example:

```php
$snippet->setAuthor('Tintin'.random_int(1, 99));

// Compute all changesets
$uow->computeChangeSets();

// Or for this entity only
$uow->computeChangeSet($this->entityManager->getClassMetadata(Article::class), $snippet);

// Then get it, we have the field modified as the key which has for value
// an array with the old as first item and new value as the second item
// try it!
$changeset = $uow->getEntityChangeSet($snippet);

// And what is the state of this entity?
switch ($uow->getEntityState($snippet)) {
    case UnitOfWork::STATE_MANAGED:
        echo 'Snippet is managed (already in DB).';
        break;
    case UnitOfWork::STATE_REMOVED:
        echo 'Snippet is going to be removed.';
        break;
    case UnitOfWork::STATE_DETACHED:
        echo 'Snippet is detached.';
        break;
    case UnitOfWork::STATE_NEW:
        echo 'Snippet is new.';
        break;
}
```
