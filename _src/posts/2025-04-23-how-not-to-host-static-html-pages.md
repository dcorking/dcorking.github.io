    Title: How NOT to host static HTML pages
    Date: 2025-04-23
    Tags: DRAFT, ruby, heroku, containers, html

There are many plain and simple webservers that you can run on your computer
(or smaller device) to serve a few web pages, images or JavaScript.
These can be handy for development, but don't try to run one in a container
on the live net, such as in a Heroku dyno. Forget that advice for a moment
and try it anyway!

<!-- more -->

Not every website on your laptop needs a professional web
server such as Apache or Nginx. Can we just throw up some pages on Heroku
without an application server like puma or unicorn, nor a responder like
sinatra or express, or even middleware like rack? You probably
shouldn't, but you can.

A few years ago I tried putting a pure ruby HTTP server on Heroku.
This helped me understand the service that a Heroku dyno actually
provides. A Heroku dyno is a form of Linux container. When I first
encountered Heroku, it seemed almost magical: make a Ruby on Rails
app, type git push, and a dyno fires up, containing your new app, and
serves pages to the public net.

The dyno appears to be a fully fledged Linux server, yet it fires up
in seconds, and is dedicated to doing just one thing: running the
Rails web server (which these days is a program called puma). When the server stops, the dyno goes away.

Since then I began to take it all for granted: concerning myself
primarily with the app itself, whether it be an Express or Rails
server, or a Sidekiq process for background jobs.

Then one day I became curious. Rather than relying on someone else's
config, I asked, can I send a small piece of code to Heroku and get
some web pages back?
