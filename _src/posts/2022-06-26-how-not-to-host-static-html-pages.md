    Title: How NOT to host static HTML pages
    Date: 2022-06-26T21:23:33
    Tags: DRAFT, ruby, heroku, containers, html

There are many plain and simple webservers that you can run on your computer
(or smaller device) to serve a few web pages, images or JavaScript.
These can be handy for development, but don't try to run one in a container
on the live net, such as in a Heroku dyno. Forget that advice for a moment
and try it anyway!

<!-- more -->

Not everything website on your laptop needs a professional web
server such as Apache or Nginx. Can we just throw up some pages on Heroku
without an application server like puma or unicorn, nor a responder like
sinatra or express, or even middleware like rack? You probably
shouldn't, but you can.
