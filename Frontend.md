# Frontend

Compiling all the frontend related content from the main page.

## HTML

### Downloading with a different filename than what it's original name on the server
```
 <a href="/orginal_name.pdf" download="New name">
```

### Embedding youtube videos
Original link : https://www.youtube.com/watch?v=1ArKekKqg2o
```
  <iframe width="420" height="315" src="https://www.youtube.com/embed/1ArKekKqg2o" frameborder="0" allowfullscreen></iframe>
```
### Facebook meta tags

```
 <meta property="og:title" content="<title>" />
 <meta property="og:type" content="<type>" />
 <meta property="og:url" content="=<link to website>" />
 <meta property="og:image" content="<path to image>" />
 <meta property="og:description" content="<text description>" />
```


## CSS

### Vertically Aligning text next to an image.
There is a huge misconception that the vertical align property has to be applied to the text. It should in fact be applied to the image.
```
	<a href="https://github.com/Sparshith" class="github">
		<img style="vertical-align: middle" src="github.png">
		<span> GitHub </span>
	</a>
```


### Specifying font-weights while using google fonts

```
	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=PT+Sans:400,500,700">
```

### iOS fix for default blur added to disabled input
```
	-webkit-text-fill-color:#f4ee42
	-webkit-opacity:1
```

### Horizontal border with text
Useful when you want an OR border.

```
<div style="width: 100%; margin-top: 20px; margin-bottom: 40px; height: 20px; border-bottom: 1px solid black; text-align: center">
      <span style="font-size: 30px; background-color: #F3F5F6; padding: 0 10px;">
	OR
      </span>
</div>
```

## Twig

### Set value inside if-else conditions.
```
 {%  if active_flag %}  {%  set checked_var = 'checked' %}   {% else %} {% set checked_var = '' %} {% endif %} 
 
```
