## Parent and Child Elements

### Can separate elements of HTML

```html
<style>
	div {
		color: blue;
		font-family: cursive;
	}

	ul {
		color: red;
	}
</style>

<div>
	<h2>Grocery List</h2>
	<h4>- the three c's</h4>

	<ul>
		<li>Coffee</li>
		<li>Cheese</li>
		<li>Chips</li>
	</ul>
</div>
```

![Image](https://github.com/wesleywesvo/Notes/blob/main/Images/Grocery%20List%201.png)

## Class Selectors

### Use an ID selector `#id` followed by its element type to identify which element to separate

### This class will affect all `<p>` elements underneath `<div> #main-content`: the 'main content' and the nested `<p>`

```html
<style>
	#main-content p {
		color: limegreen;
	}
</style>

<p>Paragraph outside of the main content.</p>

<div id="main-content">
	<h2>This is the main content</h2>
	<p>Vivamus</p>

	<div>
		<h3>This is an h3 tag nested in another div</h3>
		<p>
			This paragraph isn't a direct child of the #main-content id, it is a
			descendant
		</p>
	</div>

	<p>Proin.</p>
</div>
```

![Image](https://github.com/wesleywesvo/Notes/blob/main/Images/child%20selectors%201.png)

### To avoid the `<p>` from the nested `<div>` (its descendant), use a `>` symbol

```html
<style>
	#main-content > p {
		color: limegreen;
	}
</style>

<p>Paragraph outside of the main content.</p>

<div id="main-content">
	<h2>This is the main content</h2>
	<p>Vivamus</p>

	<div>
		<h3>This is an h3 tag nested in another div</h3>
		<p>
			This paragraph isn't a direct child of the #main-content id, it is a
			descendant
		</p>
	</div>

	<p>Proin.</p>
</div>
```

![Image](https://github.com/wesleywesvo/Notes/blob/main/Images/child%20selectors%202.png)
