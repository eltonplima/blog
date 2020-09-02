---
layout: post
title:  "Running SMTP server in development environment with python"
date:   2020-09-01 18:02:29 +0100
categories: python smtp
comments: true
---

Sometimes we need to test a code responsible for send emails, did you know that's possible to create your own email server with a single command? And all do you need is the python.

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

You can test with your code or using telnet:

{% highlight shell %}
$ telnet 192.168.0.145 2500
Trying 192.168.0.145...
Connected to 192.168.0.145.
Escape character is '^]'.
220 y740 Python SMTP proxy version 0.3
HELO demo.example.com
250 y740
mail from: user@example.com
250 OK
rcpt to: another.user@example.com
250 OK
data
354 End data with <CR><LF>.<CR><LF>
Hey 
This is my test email

Thanks
.
250 OK
quit
221 Bye
Connection closed by foreign host.
{% endhighlight %}

On the smtpd terminal you will see something like that:

{% highlight shell %}
Incoming connection from ('192.168.0.145', 42860)
Peer: ('192.168.0.145', 42860)
Data: b'HELO demo.example.com'
Data: b'mail from: user@example.com'
===> MAIL from: user@example.com
sender: user@example.com
Data: b'rcpt to: another.user@example.com'
===> RCPT to: another.user@example.com
recips: ['another.user@example.com']
Data: b'data'
Data: b'Hey\r\nThis is my test email\r\n\r\nThanks'
---------- MESSAGE FOLLOWS ----------
b'Hey'
b'This is my test email'
b'X-Peer: 192.168.0.145'
b''
b'Thanks'
------------ END MESSAGE ------------
Data: b'quit'
{% endhighlight %}

{% if page.comments %}
<div id="disqus_thread"></div>
<script>
let disqus_config = function () {
    this.page.url = 'https://blog.eltonplima.dev';
    this.page.identifier = '3bc69473-580d-4e91-9f1b-9f0b77843ae1';
};

(function() {
    let d = document, s = d.createElement('script');
    s.src = 'https://blog-eltonlima-dev.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
