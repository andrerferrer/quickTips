[go back](https://github.com/andrerferrer/quickTips#quicktips)

```erb
<%= simple_form_for @restaurant do |f| %>
  <%= f.input :name %>
  <%= f.input :address %>
  <%= f.button :button do %>
    <i class="fas fa-plus-square"></i>
  <% end %>
<% end %>
```
