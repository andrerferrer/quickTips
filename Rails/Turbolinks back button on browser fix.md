[go back](https://github.com/andrerferrer/quickTips#quicktips)

## Turbolinks back button on browser fix

Add to your `app/views/layouts/application.html.erb` on the head:

```erb
<html>
  <head>
    <title>A Title</title>

    <%# This might prevent turbolinks cache %>
    <!-- Add this line -->
    <meta name="turbolinks-cache-control" content="<%= yield(:turbolinks_cache) %>"> 
    <!-- Add this line -->
```

On the corresponding page (the one that's bugging when you go back), add this in the beginning of the file:

```erb
<%# This prevents turbolinks cache %>
<%= provide(:turbolinks_cache, 'no-cache') %>

<%# This solution was implemented from this thread https://stackoverflow.com/questions/39627881/jquery-plugin-initialization-on-browser-back-button-for-turbolinks-rails-5/39801052#39801052 %>
```

And that's it!

Good Luck Have Fun
