[go back](https://github.com/andrerferrer/quickTips#quicktips)

## Show/Remove Navbar/Footer only on certain pages

Add a [new layout](https://guides.rubyonrails.org/layouts_and_rendering.html) and call it in the controller
```ruby
class Controller < ApplicationController
  layout 'my_layout_without_a_footer', only: [:new, :index]
```

If we want it to not show on users new and edit, with [devise](https://github.com/heartcombo/devise), we need to [expose the controller](https://github.com/heartcombo/devise#configuring-controllers).