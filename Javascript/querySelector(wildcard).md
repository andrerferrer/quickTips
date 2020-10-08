[go back](https://github.com/andrerferrer/quickTips#quicktips)

## [How to query select with wildcard?]

[reference](https://stackoverflow.com/questions/8714090/queryselector-wildcard-element-match)

Eg. Imagine that we want to select all elements whose ID starts with `restaurant-`

We can `document.querySelector("[id^='restaurant-']")` will match all ids starting with `restaurant-`.

We can also use:

- `[id$='restaurant-']` will match all ids ending with `restaurant-`.
- `[id*='restaurant-']` will match all ids containing `restaurant-`.