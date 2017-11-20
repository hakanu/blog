---
published: true
layout: post
category: python
title: Using vue.js with Jekyll - double curly brace problem
---
If you are go full serverless, means you need to do lots HTML templating and Javascript juggling. 
For making templating easier (of course you can always do single page with vue.js and vue-router but I don't like it for SEO purposes), I started to use Jekyll's liquid templating system with proper layouts and includes. However, liquid uses double curly braces for templating just like vue.js template delimiters. This means that liquid will strip out all my vue.js tags at the time of the generation. This ended up no vue rendering. In order to solve this problem:

- I tried changing Vue delimiters to `[[ ]]` instead of `{{ }}` -> Sadly didn't resolve.

`Vue.config.delimiters = ['$[', ']']`

- Not cool but I tried using `{% raw %}` tags of jekyll to let `{{}}` go without being stripped out. And it worked.

```html
{% raw %}
<p>{{ title }}</p>
{% endraw %}

```

in JS file:

```js
data: {
  title: 'Who let the dogs out'
}
```
