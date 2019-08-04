# WP Theme Mini Docs

## Generating Theme Template

Generate theme from [underscores.me](https://underscores.me/).

```header.php```  - Include website header here.

Create assets folder and paste all assets there.

```
bloginfo( 'stylesheet_directory' );
```

Add stylesheet directory to complete assets url

```footer.php``` - Include website footer here

```sidebar.php``` - Add sidebar here

from ```page.php``` save it as ```page-home.php```

Inside ```page-home.php``` add this

```
<?php /* Template Name: Home Page */ ?>
```

Add Home Page content inside ```page-home.php```

Goto Admin Dashboard, and goto pages, create a page with **Home Page** Template

## Essential Variables

```bloginfo( 'name' )``` - Shows Website Name

```bloginfo( 'description' )``` - Shows Website Description

## Creating Custom Fields

Inside ```Screen Options``` select ```Custom Fields```

Inside Custom Fields add whatever you want

get Custom Fields data using

```
get_post_meta(post_id, variable, true)
```

## Advanced Custom Fields

Install Plugin

Add Variables inside ADV tab

Get data using

```
get_field(variable_name)
```

## Custom Post Type using

Install Plugin

Create a custom post type

and add variables using Advanced Custom Fields

```
$args = array(
    'post_type' => 'lirik_melayu',
    'posts_per_page'=> -1,   // set the limit post to UNLIMITED (-1 is unlimited)
    'orderby'  => array( 
            'ID' => 'DESC' ,
        ),
);
$query = new WP_Query( $args );
$query_contents=Array();
while ( $query->have_posts() ) {
    $query->the_post();
    array_push($query_contents,Array(
        "id"=>get_the_ID(),
        "title"=>get_the_title(),
        "url"=>get_permalink(),
    ));
    echo get_the_title()."<br />";
}
```

### Edit Blog Template

```content.php``` - It contains the blog template

```content-single.php``` - It contain single page blog template