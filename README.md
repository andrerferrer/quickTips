# quickTips

This is a repository with some quick tips. 

[Also check my demos.](https://github.com/andrerferrer/dedemos)

## General Resources - Some nice links and tools
### [Excel to Array](https://www.seabreezecomputers.com/excel2array/)
### [Git Troubleshooting Cheatsheet](https://ohshitgit.com/)

## Git && Github
### - [Git pull rebase (PT-BR)](https://pt.stackoverflow.com/questions/279562/qual-a-diferen%C3%A7a-entre-git-pull-e-git-pull-rebase)
### - [Find the Root of the repo](https://stackoverflow.com/questions/957928/is-there-a-way-to-get-the-git-root-directory-in-one-command)

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

### [Create a link to nowhere in rails](https://stackoverflow.com/questions/12081156/rails-using-link-to-to-make-a-link-without-href)

```ruby
content_tag 'a', "text"
```

it generates:

```HTML
<a>text</a>
```

You an also create a `link_to` nowhere

```ruby
link_to 'Click me', 'javascript:;'
```

`javascript:;` is the Javascript no operator. 

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

##### 1. With `display:flex` :

Use a `display: flex` to make the content take all the available space that is not the footer. 

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

## Javascript

### [How to query select with wildcard?](https://stackoverflow.com/questions/8714090/queryselector-wildcard-element-match)

Eg. Imagine that we want to select all elements whose ID starts with `restaurant-`

We can `document.querySelector("[id^='restaurant-']")` will match all ids starting with `restaurant-`.

We can also use:

- `[id$='restaurant-']` will match all ids ending with `restaurant-`.
- `[id*='restaurant-']` will match all ids containing `restaurant-`.

