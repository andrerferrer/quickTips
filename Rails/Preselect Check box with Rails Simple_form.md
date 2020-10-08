[go back](https://github.com/andrerferrer/quickTips#quicktips)

### Preselect Check box with Rails Simple_form

The case: Imagine that we want to Preselect Check box with Rails Simple_form. How can we do it?

We need to pass a `checked` value to the input:

```erb
<%= f.input :notify, label: "Notification", as: :check_boxes, collection: ["None", "Daily", "Weekly", "Monthly", "Quarterly", "Yearly"], :item_wrapper_class => 'inline', :checked => ["None", true] %>

```

Sources:
https://github.com/heartcombo/simple_form/issues/643
https://stackoverflow.com/questions/4116415/preselect-check-box-with-rails-simple-form