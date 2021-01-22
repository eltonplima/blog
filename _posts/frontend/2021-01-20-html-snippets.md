---
title:  "Frontend snippets and tips"
date:   2021-01-20 16:15:21 +0100
categories: frontent
layout: post
---

# Frontend snippets and tips

## Submit A Form With A Button Outside The Form

{% highlight html %}
<div>
  <form id="my-form">
    <label for="name">Name:</label>
    <input type="text" name="name"></input>
  </form>

  <!-- ... -->

  <button type="submit" form="my-form">Submit</button>
</div>
{% endhighlight %}

[Original source](https://til.hashrocket.com/posts/v2s2gxgifj-submit-a-form-with-a-button-outside-the-form)
