---
layout: page
title: "JavaScript is_resource function"
comments: true
sharing: true
footer: true
sidebar: false
alias:
- /functions/view/is_resource:781
- /functions/view/is_resource
- /functions/view/781
- /functions/is_resource:781
- /functions/781
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's is_resource

{% codeblock var/is_resource.js lang:js https://raw.github.com/kvz/phpjs/master/functions/var/is_resource.js raw on github %}
function is_resource (handle) {
  // http://kevin.vanzonneveld.net
  // +   original by: Brett Zamir (http://brett-zamir.me)
  // +   improved by: Luis Salazar (http://www.freaky-media.com/)
  // *     example 1: is_resource('a');
  // *     returns 1: false
  var getFuncName = function (fn) {
    var name = (/\W*function\s+([\w\$]+)\s*\(/).exec(fn);
    if (!name) {
      return '(Anonymous)';
    }
    return name[1];
  };
  return !(!handle || typeof handle !== 'object' || !handle.constructor || getFuncName(handle.constructor) !== 'PHPJS_Resource');
}
{% endcodeblock %}

 - [view on github](https://github.com/kvz/phpjs/blob/master/functions/var/is_resource.js)
 - [edit on github](https://github.com/kvz/phpjs/edit/master/functions/var/is_resource.js)

### Example 1
This code
{% codeblock lang:js example %}
is_resource('a');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
false
{% endcodeblock %}


### Other PHP functions in the var extension
{% render_partial _includes/custom/var.html %}
## Legacy comments
These were imported from our old site. Please use disqus below for new comments
<div style="overflow-y: scroll; max-height: 500px;">
{% render_partial functions/is_resource/_comments.html %}
</div>
