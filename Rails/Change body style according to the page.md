[go back](https://github.com/andrerferrer/quickTips#quicktips)

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