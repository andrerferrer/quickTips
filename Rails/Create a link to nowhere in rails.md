[go back](https://github.com/andrerferrer/quickTips#quicktips)

[reference](https://stackoverflow.com/questions/12081156/rails-using-link-to-to-make-a-link-without-href)

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