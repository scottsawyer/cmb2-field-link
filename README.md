# CMB2: Field Link #
Create a link field with some attributes.  Very nice for styling links.

## Properties ( fields ) ##
Attributes included.
- href
- text
- class
- title
- rel

## Usage ##

[Install CMB2](https://wordpress.org/plugins/CMB2/).

[Install CMB2 Field Link](https://github.com/scottsawyer/cmb2-field-link).

[Create a metabox in the usual way](https://github.com/CMB2/CMB2/wiki/Basic-Usage#create-a-metabox).

Add a link field:

```
$cmb->add_field( [
  'name' => __( 'Link Field', 'cmb2' ),
  'desc' => __( 'Create a link with some attributes.', 'cmb2' ),
  'id' => $prefix . 'link',
  'type' => 'link',
  //'repeatable' => true,
  ],
);
```

[link field example](https://github.com/scottsawyer/cmb2-field-link/raw/master/assets/images/screenshot-demo.wp-builder.net-2018.10.08-15-28-03.png)

## Accessing the link ##

Retrieve the post meta:

```
$link = get_post_meta( get_the_ID(), $prefix . 'link', true );

print_r( $link );

// Link Attributes

Array
(
    [href] => https://wordpress.org/plugins/CMB2/
    [text] => Download CMB2
    [class] => awesome class
    [rel] => nofollow
    [title] => Click me to view CMB2
)
```

You can build your link like:
```
print '<a href="' . $link['href'] . '" class="' . $link['class'] . '" rel="' . $link['rel'] . '" title="' . $link['title'] . '">' . $link['text'] . '</a>';
```

It's a good idea to test for each properties before just trying to print them.