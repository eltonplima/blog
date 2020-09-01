---
layout: post
title:  "Creating a development smtpd with python"
date:   2020-09-01 18:02:29 +0100
categories: python smtp
---
If you need a SMTP server to test your code is sending the email correctly, you only need the python.

The [python standard library](https://docs.python.org/3/library/index.html) has a lot of useful things, like the [smtpd](https://docs.python.org/3/library/smtpd.html) that allow us to run a simple [SMTP](https://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) server on our own machine in seconds.

{% highlight shell %}
LISTEN_ON_ADDRESS=localhost; LISTEN_ON_PORT=2500 && \
python -m smtpd -n -d -c DebuggingServer ${LISTEN_ON_ADDRESS}:${LISTEN_ON_PORT}
{% endhighlight %}

You'll see something like this:

{% highlight shell %}
DebuggingServer started at Tue Sep  1 18:10:46 2020
	Local addr: ('localhost', 2500)
	Remote addr:('localhost', 25)
{% endhighlight %}


[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
