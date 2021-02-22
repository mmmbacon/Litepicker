---
layout: default
nav: Predefined ranges plugin
title: "Predefined ranges plugin"
description: "Adds predefined ranges."
parent: Plugins
---

# Predefined ranges plugin

Adds predefined ranges.

Litepicker version 2.0.0 or higher is required.

{% capture ranges_video %}
<video class="demo-video" autoplay="autoplay" muted loop preload="metadata">
    <source src="{{ '/assets/video/ranges.mp4' | relative_url }}" type="video/mp4">
</video>
{% endcapture %}

{% include collapse.html title="Video" content=ranges_video %}


### Installation
{: .no_toc }

```html
<script src="https://cdn.jsdelivr.net/npm/litepicker/dist/litepicker.js"></script>
// include plugin after Litepicker
<script src="https://cdn.jsdelivr.net/npm/litepicker/dist/plugins/ranges.js"></script>
```

If you’re using a bundler, e.g. webpack, you’ll need to import Litepicker first.

```ts
import Litepicker from 'litepicker';
import 'litepicker/dist/plugins/ranges';
```

Now you can create Litepicker instance with plugin:

```html
<script>
const picker = new Litepicker({ 
  element: document.getElementById('litepicker'),
  plugins: ['ranges']
});
</script>
```

# Options

### position

Type: `String`

Default: `left`

Ranges block position.  
Possible values: `left`, `top`, `right`, `bottom`.

Example: 

```js
const picker = new Litepicker({ 
  element: document.getElementById('litepicker'),
  plugins: ['ranges'],
  ranges: {
    position: 'left'
  }
});
```

### customRanges

Type: `Object`

Default: `{ _default_ranges_ }`

Define your own ranges.  
Default ranges is: `Today`, `Yesterday`, `Last 7 days`, `Last 30 days`, `This month`, `Last month`.

Example: 

```js
const picker = new Litepicker({ 
  element: document.getElementById('litepicker'),
  plugins: ['ranges'],
  ranges: {
    customRanges: {
      'New range': [new Date('2020-11-19'), new Date()] // first start date then end date.
    }
  }
});
```

### force <sup>2.0.5+</sup>

Type: `Boolean`

Default: `false`

When `true` ignores locked days and selects a date range.

Example: 

```js
const picker = new Litepicker({ 
  element: document.getElementById('litepicker'),
  plugins: ['ranges'],
  ranges: {
    force: true
  }
});
```

{% capture ranges_content %}
<div style="display:flex">
  <input id="input-ranges" class="form-control" style="width: 250px" readonly/>
</div>
<div class="demo-wrapper" data-cfg="ranges"></div>

---

Code:

```js
new Litepicker({
  element: document.getElementById('datepicker'),
  singleMode: false,
  plugins: ['ranges']
})
```
{% endcapture %}

{% include collapse.html title="Demo" content=ranges_content %}