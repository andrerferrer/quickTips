# quickTips

This is a repository with some quick tips, mostly on HTML and CSS.

## Footer
### 1. Stick it to the bottom

The best way I've found so far is to use a `display: flex` to make the content take all the available space that is not the footer. 

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

```CSS
.wrapper {
  display: flex;
  justify-content: space-between;
  flex-direction: column;  
  min-height: 100vh;
}
```
