---
layout: post
title:  "Use Bourbon Neat Sass and Jade with Gulp for efficient Web Development."
date:   2016-02-20 15:57:35 -0500
categories: jekyll markdown sass gulp grunt scss css html5 jade bourbon neat
---

## [Project Repo](https://github.com/thestevenbell/staticWebTemplate-bourbon-neat-jade-sass-browersync)

Gulp, Jade, SASS and BrowserSync are powerful tools to make web development easier and more efficient.  A quick search on the web will tell you that Gulp is a 'task runner'.  What is a task runner and why would a task runner be necessary, you ask?  Well, Gulp comes into play when you step beyond basic HTML and CSS to use productivity tools like Jade and SASS.  Jade is a language that allows simplified, faster writing of html by doing away with angle brackets and the need for closing blocks on elements relying instead on whitespace to denote hierarchy and nesting among other things. Take a look at this [Jade tutorial by Azat Mardan](http://webapplog.com/jade/). It's better presented than the official Jade documentation and has all you need to start using Jade.  I was able to pick up Jade in a weekend while working on a front-end project – which is to say, it's a snap to pick up.  I use it as my primary markup language now because it's such an improvement over standard HTML.  Like Jade with HTML, SASS makes writing CSS easier and gives your styles super powers by allowing the use of variables and arithmetic in style sheets.  Amazing things can be accomplished with these nifty additions.

The issue with Jade and SASS is that they cannot be read by the browser.  They must first be precompiled (processed through a translator script which as the name implies takes your Jade or SASS files and rewrites them into plain old HTML or CSS which can be read by the server or browser directly). This is why you'll not see much SASS or Jade formatted code on the web. It is generally only used in development on local machines or server side where it is precompiled by the server as HTML docs are requested client side.  The raw SASS/Jade code never reaches your browser as a user.

BrowserSync reloads the page you are working on in your browser in real-time as you make changes to stylesheets or markdown.  Its functionality is incorporated into Gulp.   Talk about a time saver, especially on large format screens or multi-monitor setups where the browser is in view during development.  Detailing how to configure Gulp (which requires a bit of JavaScript coding) will be covered in a future post, but do check out the Gulpfile.js in the project repo to see how it works.   Gulp functions are fairly semantic so it should be easy to get an idea of what is going on just from reading through the file even if you are new to JavaScript.

Where the task runner Gulp comes in is at the point in time when your Jade/SASS code must be translated.  To get started the command $`gulp` is run from the terminal while in the project directory.  Gulp comes to life, precompiles your SASS and Jade assets, creates a server instance and then opens your default browser to the specified URL. You now have a local proxy of your production code and assets.  During development, the Gulp file has a .watch function which will detect when a file has been saved. If the file has been altered since the last save Gulp will run the appropriate precompiler (using either the npm module `gulp-sass` or `gulp-jade`), translate your code and save it to an .html or .css file in the directory specified in the Gulp file.  Very handy, indeed.

This repo contains all of the elements needed to begin development on a static web site using the power of the gulp task runner with LiveReload, Jade and Bourbon with Neat. Assumes you are coding on IOS with Ruby, NodeJS and NPM installed and up to date. Elements from the [Initilizr Project](http://www.initializr.com/) [Initilizer GitHub Repo](https://github.com/verekia/initializr-template) are included, namely the header elements for cross browser support and normalize.css.

### Tech Tools:
- Jade
- Bourbon with Neat
- Sass
- BrowserSync
- Node

### Some resourses:
- [using-bourbon-neat-with-gulp](https://laravel-news.com/2014/03/using-bourbon-neat-with-gulp/)
- [getting-started-with-gulp-and-sass](http://ryanchristiani.com/getting-started-with-gulp-and-sass/)
- [Bourbon Neat](https://github.com/thoughtbot/neat#requirements)
- [Gulp's GitHub Repo](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md)
- [Using Jade with Gulp](http://codepen.io/mgmarlow/post/using-jade-with-gulp)
- [Setting Up Glup with Jade, Coffee and Sass/Scss](https://www.codementor.io/development-process/tutorial/how-to-set-up-gulp-beginner-guide)
- [LiveReload - sparse directions :frown](https://www.npmjs.com/package/livereload)

### Directions for use:
- cd into your working folder
- clone or copy this repo into working folder
- run the following in bash:

    $ `npm install --global gulp-cli`         <-- installs gulp-cli globally

    $ `npm install --global gulp` <-- installs gulp globally

    $ `gem install sass`   # or `gem update sass` if you have sass already

    $ `gem install bourbon`  <-- installs bourbon on your system

    $ `gem install neat`

    $ `npm init`  <-- initilizes this project with NPM

    $ `npm install`  <-- installs the file dependencies included in the package.json file

    $ `gulp serve` <-- use this command to start gulp services.  This will automatically
    open your server at localhost and precompile SASS and Jade assets on save allowing for
    instantaneous in-browser views of updates.


- The following steps were used to create the file contents of this repo:

    $ `bourbon install`  <-- install bourbon dependency files in your working directory

    $ `neat install`

    $ `npm install --save-dev gulp`

    $ `npm install --save-dev gulp-sass`

    $ `npm install --save-dev gulp-jade`

    $ `npm install --save-dev gulp-util`

    $ `npm install --save-dev gulp-load-plugins`

    $ `npm install --save node-bourbon`

    $ `npm install —-save node-neat`

    $ `npm install —-save bourbon`

    $ `npm install --save-dev browser-sync`



### Directory Structure and File Explanation:
<-- In progress -->
website/  <-- the main working directory, name this whatevs you would like
  .sas-cache  <-- auto generated by gulp, don't touch, not used directly by developer
  /bourbon  <-- auto generated by running the $ `boubon install` command, contains the mixins used by bourbon, don't touch
  /img  <-- includes custom favicons.  replase these with your own but be sure to keep the names the same

- create index.jade file (an index.html will be generated by Gulp/Jade task) after precompiling the Jade formatted doc.

- create website/stylesheet/style.scss
  - add the following to your styles.scss
     ```
     @import "../bourbon/bourbon";
     @import "../neat/neat";
    ```

### Automation
- Gulp is set up to automate the precomplitation of resources and open the browser with
browsersync.  Simply input $ `gulp` in the command line.
- If you do not want to open the browser and use live reload it is possible to
initiate only the precompilers independently.
 - To precompile SASS use $ `gulp styles`
 - To precompile Jade use $ `gulp jade`
 - To only run the server $ `gulp serve`

##### [Made by Steven Bell](http://thestevenbell.github.io/)

hosted by GitHub, powered by [Jekyll](http://jekyllrb.com/)
