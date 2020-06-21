# quickTips

This is a repository with some quick tips. 

[Also check my demos.](https://github.com/andrerferrer/dedemos)

## General Resources
### [Excel to Array](https://www.seabreezecomputers.com/excel2array/)
### [Git Troubleshooting Cheatsheet](https://ohshitgit.com/)

## Rails
### [Schema.rb into schema draw](https://dbdiagram.io/d)

### Show/Remove Navbar/Footer only on certain pages

Add a [new layout](https://guides.rubyonrails.org/layouts_and_rendering.html) and call it in the controller
```ruby
class Controller < ApplicationController
  layout 'my_layout_without_a_footer', only: [:new, :index]
```

If we want it to not show on users new and edit, with [devise](https://github.com/heartcombo/devise), we need to [expose the controller](https://github.com/heartcombo/devise#configuring-controllers).

### Change body style according to the page

The case: Imagine that we want to implement a different bg-color certain pages. How can we do it?

In the `app/views/layouts/application.html.erb`, we can add to the `body`:
```erb
<body class="<%= action_name > <%= controller_name >">
```

Hence, we can apply the css according to the controller and action:
```CSS
body.pages.home {
  /* Style for the body on pages home */
}

body.pages.about {
  /* Style for the body on pages about */
}
```

## CSS

### Position: Absolute
#### Centralize it
```CSS
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  //If needed
  //text-align: center;
```

### Footer

#### Stick it to the bottom

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
