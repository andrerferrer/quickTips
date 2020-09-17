[go back](https://github.com/andrerferrer/quickTips#quicktips)

#### Stick it to the bottom

##### 1. With `display:flex` :

Use a `display: flex` to make the content take all the available space that is not the footer. 

The HTML:
```HTML
<div class="wrapper">
  <div id="content-goes-here"> <!-- the id here is just to remind you -->
    Insert your content here
  </div>
  <div id="footer-goes-here"> <!-- the id here is just to remind you -->
    Insert your footer here
  </div>
</div>
```

The CSS:
```CSS
.wrapper {
  display: flex;
  justify-content: space-between;
  flex-direction: column;  
  min-height: 100vh;
}
```

##### 2. With `display:grid` :
Use a `display: grid`:

The HTML:
```HTML
<div class="wrapper">
  <div class="content">
    Insert your content here
  </div>
  <div class="footer">
    Insert your footer here
  </div>
</div>
```

The CSS:
```CSS
.wrapper {
  display: grid;
  grid-template-rows: auto 1fr auto;
  min-height: 100vh;
}
```

##### 3. Other solutions:

- [With position absolute](https://www.freecodecamp.org/news/how-to-keep-your-footer-where-it-belongs-59c6aa05c59c/).