# Jekyll-mermaid

A [Jekyll](http://jekyllrb.com/) plugin to simplify the creation of [mermaid](https://github.com/knsv/mermaid) diagrams and flowcharts in your posts and pages.


## Installation

1. Install the gem:
  ```bash
  gem install jekyll-mermaid
  ```

2. Add the gem to your Jekyll `_config.yml`:
  ```ruby
  gems: [jekyll-mermaid]
  ```

Please see the [Jekyll documentation](http://jekyllrb.com/docs/plugins/#installing-a-plugin) for more installation options.


## Config

You'll need to update your `_config.yml` with the location of the [mermaid](https://github.com/knsv/mermaid) source javascript file you want to use.

```ruby
mermaid:
  src: 'path/to/mermaid.js'
```

## Jekyll Hint

To get the CSS for this page you may want to make a few additions

### Front matter variable
You may want to add a custom variable `mermaid` to make sure the CSS applies only to pages that need it.
```ruby
---
layout: post
title:  "Your awesome title!"
mermaid: true
---
```

### Mermaid CSS addition
[CDNJS mermaid](https://cdnjs.com/libraries/mermaid) is a good source to add to your page.

```html
{% if page.mermaid %}
<script type="text/javascript">
    // your custom JS for mermaid, goes here
</script>

<link rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/mermaid/7.0.0/mermaid.forest.min.css">
<!--href="or/path/to/your/local/mermaid/css">-->

<style>
    /* same sample CSS changes if needed */
    .mermaid {
        margin: auto;
        overflow: auto;
        width: 100%;
        overflow-x: visible;
        border: 3px solid #73AD21;
        padding: 10px;
        text-align: center;
    }
</style>
{% endif %}
```

## Usage

Simply include the [jekyll-mermaid](https://github.com/jasonbellamy/jekyll-mermaid) block helper in any of your templates.

```liquid
{% mermaid %}
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
{% endmermaid %}
```

Please see the [mermaid documentation](https://github.com/knsv/mermaid/wiki) for more examples.


## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality.


## License
Copyright (c) 2014 [Jason Bellamy ](http://jasonbellamy.com)
Licensed under the MIT license.
