# thestevenbell.github.io
Website, Projects and Portfolio for Steven Bell

### !!! IMPORTANT - YOU MUST WORK IN THE GH_PAGES BRANCH USE -->$`git checkout gh-pages`
#### this blog is hosted at thestevenbell.github.io/devicurious

#### Developement:
to compile and serve locally:  $ `bundle exec Jekyll serve`

#### Directions for using this Jekyll based blog engine on GitHub Pages.

- add blog posts by renaming the file to fit the naming convention:
2016-02-20-static-site-template-with-jade-sass-gulp-bourbon-neat.md
(yr-mo-day-name.md)

- Add the file to the _posts directory

----------------
Checkout the Jekyllrb [wiki](https://github.com/mojombo/jekyll/wiki) for documentation on writing posts. This theme
makes use of static sharing buttons and they use a few tags that you should include in your posts.
An example of a post header:

    ---
    layout: post
    title:  "minimal-block - A minimalistic responsive Jekyll theme"
    date:   2015-01-25 00:00:00
    categories: jekyll, themes   <-- these are tags that will be displayed on the blog above the post title.
    tags: jekyll, theme, minimal
    shortUrl:
    ---

Most of these variables are just the default ones but the last two (`tags` and `shortUrl`) are used by the theme when sharing via the social buttons in the end of every post.

Specifically, `tags` will be converted into hashtags when sharing on Twitter and if you supply a `shortUrl`, it will be used instead of the full url. This is useful if you are using [goo.gl](http://goo.gl) since they provide statistics for each short link and that way you can see how many people are sharing your post.


Pages and other files.
----------------
Each page has its own directory in the root folder of the theme. In each directory there is an index.html representing the contents of the page. Take a look at the default ones (about and contact) to see the structure.

Another file to know about is the `footer.html` as it has the copyright notice and credits. This file is located in the `_includes` folder. You can remove the credits if you want but I would love you if you give me some credit in the HTML source.

The `404` file is located in the root folder and it contains the exactly same structure as a page.
