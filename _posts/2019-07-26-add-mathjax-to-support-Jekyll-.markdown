---
layout: post
title: add mathjax to support Jekyll
tags: [frontpage, jekyll, blog]
mathjax: true
---
Solution was found in [Brendan AR Sechter's Development Blog](http://sgeos.github.io/github/jekyll/2016/08/21/adding_mathjax_to_a_jekyll_github_pages_blog.html)

---

Steps:

Add mathjax.html file to _includes, the file need to be edited in Xcode (cannot use TextEdit since some codes will not be displayed in TextEdit). The following codes is added inside header. 

{% highlight js %}
{% if page.mathjax %}
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
tex2jax: {
inlineMath: [ ['$','$'], ["\\(","\\)"] ],
processEscapes: true
}
});
</script>
<script
type="text/javascript"
charset="utf-8"
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
>
</script>
<script
type="text/javascript"
charset="utf-8"
src="https://vincenttam.github.io/javascripts/MathJaxLocal.js"
>
</script>
{% endif %}
{% endhighlight %}

Add the following line the _layouts/post.html

{% highlight js %}
{% raw %}{% include mathjax.html %}{% endraw %}
{% endhighlight %}

Add the following line to the header of a post

{% highlight js %}
mathjax: true
{% endhighlight %}
