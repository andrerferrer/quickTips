[go back](https://github.com/andrerferrer/quickTips#quicktips)


```erb
<%= simple_form_for @restaurant, html: { style: 'color: red;' } do |f| %>
  <%= f.input :name %>
  <%= f.input :address %>
  <%= f.submit %>
<% end %>
```
