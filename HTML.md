# HTML

## Header Semantics

#### Do not skip a header size

#### Typically only have one `h1` on a page

## Header Syntax

#### Used to make your text stand out in a document ie: titles

#### Help search engines to index and determine contents of a page

#### Opening and closing `<h#> </h#>` tags

#### Numerical tag `1-6` is the header's size

```html
<h1>Always be coding...</h1>
<h2>Always be coding...</h2>
<h3>Always be coding...</h3>
<h4>Always be coding...</h4>
<h5>Always be coding...</h5>
<h6>Always be coding...</h6>
```

## Paragraph Elements

### Supports nested inline elements

### Opening and closing `<p> </p>` tags

## Block-Level Elements

### Take up the full width of a document and "blocks out" elements to its left and right

### Common block elements:

##### \* Headers `<h#> </h#>`

##### \* Forms`<form>`

##### \* Divisions `<div>`

##### \* List and list items `<ol>, <ul, <li>`

##### \* Paragraphs <p>

## Inline Elements

### Elements stay on the same line and do not consume available width

### Common inline elements:

##### \* Spans `<span>`

##### \* Images `<img>`

##### \* Anchors (links) `<a>`

# Attributes

## Syntax/Notes

### Appear inside opening tag of an element

### Sits inside quotation marks (similar to a string)

```HTML
<tag attributeName= 'the value'> CONTENT </tag>
```

## Applying Attributes

### Example with input types

```HTML
<input type='file'>
<hr> <!-- hr (horizontal rule) adds a line break -->
<input type='color'>
<hr>
<input type='checkbox'>
<hr>
<input type='radio'>
<hr>
<input type='date'>
```

# HTML File Creation

## `<head> </head>`

### `<script> </script>` Runs the specified file within `script` tag

#### \* type= file extension src= file name

### `<meta (content ex: name-'wesley')>` provides information about web page without displaying it

## `<body> </body>` Appears underneath the `head` tag

```HTML
<!DOCTYPE html>
<html>
    <head>  <!-- The 'head' is the name of the tab that will open in browser -->
        <title> My First Page </title>

        <meta name='wesley'>

        <script type="text/javascript" src="example.js"></script>
    </head>
    <body>
        <h1> Testing Title H1 Header </h1>
    </body>


</html>

```
