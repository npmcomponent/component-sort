*This repository is a mirror of the [component](http://component.io) module [component/sort](http://github.com/component/sort). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/component-sort`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*

# sort

  Sort DOM elements

## Installation

    $ component install component/sort

## API

### sort(el, fn)

  Sort element ascending with the given callback function.

### sort.asc(el, fn)

  Alias of `sort(el, fn)`

### sort.desc(el, fn)

  Sort descending, inverting the `fn()` return value.

## Example

```html
<ul>
  <li>Tobi</li>
  <li>Jane</li>
  <li>Abby</li>
  <li>Loki</li>
  <li>Simon</li>
  <li>Manny</li>
  <li>Luna</li>
</ul>

<button onclick='asc()'>Sort ascending</button>
<button onclick='desc()'>Sort descending</button>

<script src="build/build.js"></script>
<script>
  var sort = require('sort');
  var ul = document.querySelector('ul');

  function alpha(a, b){
    a = a.textContent;
    b = b.textContent;
    if (a < b) return -1;
    if (a > b) return 1;
    return 0;
  }

  function asc() {
    sort(ul, alpha);
  }

  function desc() {
    sort.desc(ul, alpha);
  }
</script>
```

## License

  MIT
