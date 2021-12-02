[go back](https://github.com/andrerferrer/quickTips#quicktips)

## Problem

If you have a link to another page with an anchor, turbolinks can get in the way.

## Solution: Disable turbolinks on a Button

```html
<a href="/next" data-turbolinks='false' >Next</a>
```

```erb
<a href="/next" data-turbolinks='false' >Next</a>
<%= link_to 'Next', next_path, data: { turbolinks: false }  %>
```

### Sources
- https://github.com/turbolinks/turbolinks/issues/214
- https://github.com/turbolinks/turbolinks/pull/348
