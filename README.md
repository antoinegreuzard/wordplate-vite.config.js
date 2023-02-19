# vite.config.js which works with WordPlate for better image loading

## Images call in CSS and PHP

### CSS

```
background-image: url('../static/img/test.png');
```

### PHP

```
In functions.php :
function get_image_path($image): string {
    if (is_array(wp_remote_get('http://localhost:5173/'))) {
        $hrefImages = "http://localhost:5173/resources/static/img/$image";
    } else {
        $hrefImages = get_theme_file_uri("assets/img/$image");
    }
return $hrefImages;

}


In template.php :
get_image_path('test.png');
```
