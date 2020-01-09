# Symfony

### Project setup

```text
composer self-update 
composer create-project symfony/skeleton example_project 
cd example_project 

Start server: 
php -S 127.0.0.1:8000 -t public OR 
composer require server 
php ./bin/console server:run OR php ./bin/console server:start
```

### PHPStorm config:

* Go to Preferences, Plugins, then click "Browse Repositories". 
* Search for "Symfony Plugin". You should also download "PHP Annotations" and "PHP Toolbox". 
* Then, come back to Preferences, search for "symfony" and find the new "Symfony" section. Click the "Enable Plugin" checkbox: you need to enable the Symfony plugin for each project.
* Change the "web" directory to public. Then: composer require asset - This is not required, but it will give us more auto-completion when working with assets.
* Search "Composer" and click on the "Composer" section. Click to browse for the "Path to composer.json" and select the one in our project. Thanks to this, PhpStorm will make it easier to create classes in src/.

### Useful packages to install from start:

* `composer require twig` 
* `composer require debug --dev` - The profiler also installed Symfony's var-dumper component: dump\($var\); In Twig, you're allowed to use dump\(\) with no arguments, because it dumps an associative array of all of the variables you have access to. Every template gets 'app' variable.
* `composer require annotations` - instead of /config/routes.yaml use  /_\* @Route\("/{slug}", name="route\_name", methods={"POST"}\) \*_/ comment. When you auto-complete the @Route annotation, be sure to choose the one from `Symfony\Component\Routing` composer
* `require maker --dev`- enables easy creation for stuff with `php bin/console make:command`

### Controllers:

* As soon as you want to render a template, your controller need to extend a base class AbstractController. Then: `return $this->render('template', [vars])`

### Routes:

* Debug routes: `php ./bin/console debug:router`

### JSON API Endpoint:

* `return $this->json(['var' => $value]);`

### Twig:

* Whenever you link to a static asset - CSS, JS or images - you should wrap the path in this `asset()` function
* Use route name in twig:

```php
{{ path('app_article_homepage', {param: ''}) }}
```

* Append to the block: 

```php
{{ parent() }}
```

* Dont autoescape var: add `|raw` filter

### Logger service:

* Inside the controller, on the method, add an additional argument. Give it a `LoggerInterface` type hint: hit tab to auto-complete that and call it whatever you want:

```php
public function myFunction($var1, LoggerInterface $logger){
    $logger->info('Test'); //Saves to /var/log/
} 
```

### Cache service:

* Use `AdapterInterface` type casting

```php
$item = $cache->getItem('key');
if (!$item->isHit()) {
    $item->set('value');
    $cache->save($item);
}
$testContent = $item->get();
```

* Running `php ./bin/console cache:clear` clears Symfony's internal cache that helps your app run, but it purposely does not clear anything that you store in cache. If you want to clear that, run `php ./bin/console cache:pool:clear cache.app`

### Tips:

* Everything in Symfony is done by a service. Bundles give us these services... and installing new bundles gives us more services.
* All of the files inside `config/` either configure services or configure routes.
* Whenever you want to re-use some code - or just organize things a bit better - take that code and move it into its own service class.
* @ in yaml: tells Symfony not to pass us that string, but to pass us the service with that id.
* As soon as you put `@required` above a method, Symfony will call that method before giving us the object
* The container is a fancy word for a simple concept: the object that holds all of the services in app. But actually, the container can also hold a second type of thing: config values! These are called parameters.
* New projects will not have a .env.dist file. Instead, your .env file is committed to your repository and should hold sensible, but not "secret" default values. To override these defaults with values specific to your machine, create a .env.local file. This file will be ignored by git.
* If you want to see all the environment variables that are currently set, there's a handy bin/console command for that: `php bin/console about`
* Bind has two super-powers: you can bind by the argument name or you can bind by a class or interface.

### Console commands:

* Remove cache: `rm -rf var/cache/dev/*` or just `php ./bin/console cache:clear` 
* Type-hints for the services: `php ./bin/console debug:autowiring` 
* `php ./bin/console debug:container --show-private` - show full list of services
* `php ./bin/console config:dump bundle_name` - YAML config example for bundle
* `php ./bin/console debug:config bundle_name` - current bundle config 
* `composer unpack debug` - if you want to unpack the pack to individual libraries
* Click on method param, then `Alt+Enter` and select "Initialize fields" to create an property and set it

