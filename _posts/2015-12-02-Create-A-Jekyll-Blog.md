---
layout: post
title: Creating a Jekyll blog site
tags: jekyll
category: misc
---
As you are continuously learning through technologies you might want to share your knowledge with other fellow engineers. To do this you need to have a proper medium and that is through blogs. I have had the same thought and was looking for good blogging technologies where i can write blogs and publish to all.

After couple of days of research i opted for [Jekyll](http://jekyllrb.com/) and [Github](https://github.com/) as we can create nice blogs with Jekyll and publish through github. And Jekyll also has some built-in features like code highlighter will be helpful while writing blogs.

<!--more-->

The initial hurdle to get start is to select a theme for the Jekyll blog site. I spent couple of days to find out a nice slick design site which exposes only text and found this one [jekyll-qck-theme](http://qckanemoto.github.io/jekyll-qck-theme/). I choose this one and did some modifications to it to make it work for my need. You can find lot of free theme here at [jekyllthemes](http://jekyllthemes.io/).


After choosing your theme you might need the following features in it to make it more interactive with others.

* Navigation bar site to categorize blogs
* Share blogs through social media.
* Provide a way to discuss about the blog in the site.



### Navigation Bar:
 * [Bootstrap](http://getbootstrap.com/) has good support for nav bars so we can just use that to have a nav ban for desktop and mobile browsers. Use this [tutorial](https://getbootstrap.com/components/#navbar) will help in understanding nav bar and how to add them to you site.

 * Once you got now you need to generate the site so that posts can be organized into the categorizes. Jekyll has nice built-in support for categorizing posts. Define a post with the following element in the post header configuration.

 {% highlight css %}

category: misc

{% endhighlight %}

The category element of the jekyll will tell jekyll to generate this post into the folder of *misc*.

* Now you need to define a [category.html](https://github.com/tguduru/tguduru.github.io/blob/master/_layouts/category.html) in the _layouts folder as in the link.
* Create a folder named as the category (misc) and add a file as index.html with the following content
{% highlight html %}
---
layout: category
title: HBase
category: misc
hide: true
---
{% endhighlight %}
This will build a home page with all the posts in the category when you click on this categories menu bar.

* Then you can define the nav bar name and its url as follows in the default.html
{% highlight html %}
<a class="page-scroll" href="/misc">Miscellaneous</a></li>
{% endhighlight %}

### Social Integration
There are lot of ways to get your site integrated with social media but i personally like [don reach](http://donreach.com/social-share-buttons) social integration. Its very easy to integrate this one into you blog site. This also provides the ability to get counts of sharing as well.

* Include the following into your default.html

``` html
<script src="http://share.donreach.com/buttons.js"></script>
```

* Include the following html code into a a page could be as share.html and include that in the header/footer depends on whether you want to be on both header & footer both or on a single side. Include what social media you want like twitter/linkedin/google etc...

``` html

<div class="don-share" data-url="<url>" data-image="" data-style="icons" data-bubbles="hover" data-title="<page title>">
    <div class="don-share-twitter"></div>
    <div class="don-share-google"></div>
    <div class="don-share-linkedin"></div>
    <div class="don-share-reddit"></div>
    <div class="don-share-facebook"></div>
  </div>

```
All the above data items can be sent to social media like twitter/linkedin when sharing. Look for documentation on [don reach](http://donreach.com/social-share-buttons) for additional details.

###Disqus

Disqus provides great discussion forum and its easy to integrate with your blog. Add the disqus script provdied by disqus into your footer.html.
