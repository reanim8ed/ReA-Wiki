# Wordpress

###  **Change Yoast meta tags**

```php
More info: https://www.ibenic.com/programmatically-change-yoast-seo-open-graph-meta/

/**
* Function to add hooks and filter out the Yoast SEO Open Graph Meta Tags
*/
function change_yoast_seo_og_meta() {
    add_filter( 'wpseo_opengraph_title', 'change_title' );
    add_filter( 'wpseo_opengraph_desc', 'change_desc' );
    add_filter( 'wpseo_opengraph_url', 'change_url' );
    add_action( 'wpseo_add_opengraph_images', 'add_images' );
}
add_action( 'wpseo_opengraph', 'change_yoast_seo_og_meta' );

function change_title( $title ) {
  $title = __( 'Get the eBook that was read by more than 100 people', 'change_textdomain' );
  return $title;
}
function change_desc( $desc ) {
  $desc = __( 'The best eBook you can have on your laptop, tablet or smartphone. See what others are reading to improve their career.', 'change_textdomain');
  return $desc;
}
function change_url( $url ) {
  $url = add_query_arg( 'from', 'facebook', $url );
  return $url;
}
function add_images( $object ) {
  $image = 'http://url_to_our_image.png';
  $object->add_image( $image );
}
```

