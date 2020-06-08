# quickTips

This is a repository with some quick tips, mostly on HTML and CSS.

[Also check my demos.](https://github.com/andrerferrer/dedemos)

## General Resources
### [Excel to Array](https://www.seabreezecomputers.com/excel2array/)


## Rails
### Show/Remove Navbar/Footer only on certain pages

Add a [new layout](https://guides.rubyonrails.org/layouts_and_rendering.html) and call it in the controller
```ruby
class Controller < ApplicationController
  layout 'my_layout_without_a_footer', only: [:new, :index]
```

If we want it to not show on users new and edit, with [devise](https://github.com/heartcombo/devise), we need to [expose the controller](https://github.com/heartcombo/devise#configuring-controllers).

## CSS
### Footer
#### 1. Stick it to the bottom

The best way I've found so far is to use a `display: flex` to make the content take all the available space that is not the footer. 

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
  display: flex;
  justify-content: space-between;
  flex-direction: column;  
  min-height: 100vh;
}
```
