---
layout: post
title:  "Auto page reload!"
date:   2018-05-21 18:00:00 -0700
categories: page reload
---
There are various options for auto reloading your page in the browser during development. I've tried a few, but the simplest tool  that does what is needed is `webpack-dev-server`. `livereload`/`liverloadx` are easy to use, but not as great.



# webpack-dev-server
Webpack-dev-server makes web development much more convenient. It would recompile and reload the page when a change to a file is saved. When you save a file without changes, it will not reload the page.

Url: https://webpack.js.org/configuration/dev-server/

 
Usage example: `webpack-dev-server --config webpack.dev.js --progress`

 
There are two urls that you can use:

http://localhost:8080            _(default)_

http://localhost:8080/webpack-dev-server/index.html

 

The default host and port are: http://localhost:8080. However, if you are using http://localhost:8080/webpack-dev-server/index.html, then:

  * it reloads the page when you modify .ts, .js, .htm, .html
  * it preserves the input on the page after reloading only when .ts, .html files change
  * it seems to compile a bit faster then the other two commands, but I don't have any stats

Disadvantages are:
  * you do not see url address
  * if it just refreshes and does not do a full reload of the page, then api calls will not be redone

# livereload and livereloadx
These two tools are simple to use, but they are not as convenient as webpack-dev-server. You will need to add [LiveReload](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei?hl=en) extension to Chrome for them to work.

The command for both would look similar:

`livereloadx --exts htm,ts,js --exclude node_modules/* --delay 5000`

 

You would have to use the delay attribute to wait for the compilation to complete.