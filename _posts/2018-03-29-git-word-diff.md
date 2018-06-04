---
layout: post
title:  "Git word-diff"
categories: software git
updated: 2018-06-04
---

If you have the problem that you can't easily spot what has changed between two long lines of code or data when viewing the output of `git diff`, then you can use [word-diff](https://git-scm.com/docs/diff-options/#diff-options---word-diffltmodegt) which will show changes at a "word" level instead of per-line:
{% highlight bash %}
git diff --word-diff
{% endhighlight %}

It does this by having a default definition for word boundaries, but you can override this by defining your own pattern with a regular expression (or regex). With a regex pattern that matches everything (the dot) you can see changes per-character within the line:
{% highlight bash %}
git diff --word-diff-regex=.
{% endhighlight %}

The following seems to work well for JSON data where curly brackets define an object and commas separate the keys within an object:
{% highlight bash %}
git diff --word-diff-regex="[^[:space:],{}]+"
{% endhighlight %}

The default regex pattern used when you don't specify one is different per file format, but generally uses white space characters while not splitting up multi-byte unicode characters [[source](https://stackoverflow.com/questions/30428377/what-are-git-diff-word-diff-default-regexps)], for example:
{% highlight bash %}
git diff --word-diff-regex="[^[:space:]]|[\xc0-\xff][\x80-\xbf]+"
{% endhighlight %}
