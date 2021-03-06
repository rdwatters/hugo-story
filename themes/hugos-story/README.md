# Hugo Story Theme

Originally ported from [freehtml5.co's Story theme][].

A sample of the site can be found at <https://hugos-story.netlify.com>.

## Features

In additional to the style of the original theme, the following features have been added:

* Disqus comments
* [Featherlight image modal][]
* Partials for improved SEO
* Copyable code blocks via [clipboard.js][]
* Taxonomies and taxonomy pages (ie, tags and categories)
* "Share" button that can be customized in your config file
* A Gulp-based assets pipeline, including image resizing
  * From within your root directory&mdash;after installing the theme&mdash; run `cd themes/hugos-story/pipeline && npm install && gulp`*
  * When running `gulp`, images dropped into `hugos-story/source-images` will automatically be resized, optimized and added to the appropriate folders inside of `static/assets/images`.

> * **NOTE:** While I have included the Gulp asset pipeline in this theme, I *do not plan on supporting this part of theme.* YMMV. If you are unfamiliar with Gulp, I suggest you check out the [official Gulp docs].

## Configuration

The following is the full `config.toml` you should use for the theme:

```
archetypedir = "archetypes"
baseurl = "/"
buildDrafts = false
buildFuture = false
canonifyurls = true
# Pointing to this file
config = "config.toml"
contentdir = "content"
# Copyright year is auto-generated (see layouts/partials/site_footer/site_copyright.html). Use the following to change the text *after* the copyright year. If you want to stop auto-generation of copyright year, change
copyright = "Your config copyright line"
# Set to true is you don't want livereload in local development
disableLiveReload= false
# Set to false if you want rss xml files auto-generated
disableRSS = false
# Set to false if you want a sitemap.xml created at the site root
disableSitemap = false
# Set the unicode character used for the "return" link in page footnotes.
footnotereturnlinkcontents = "↩"
# Create an array of files you don't want hugo to build
ignoreFiles = []
languageCode = "en-us"
# Point the generator to the folder used for layouts and templating
layoutDir = "layouts"
# Enable Logging
log = true
# This accepts yaml, toml, or json
metaDataFormat = "yaml"
# This intelligently adds an "s" to the titles of list pages
pluralizelisttitles = false
preserveTaxonomyNames = true
# This sets the title of the directory where hugo builds and pushes the final site when running "Hugo" (ie, without "server")
publishdir = "public"
pygmentsUseClasses = true
relativeURLs = true
source = ""
theme = "hugos-story"
# This is the top-level, global site title
title = "Your Site Title"
# Set to true to convert mysite/section/ to mysite/section.html
uglyURLs = false
verbose = false
verboseLog = false
# Setting this to false will keep hugo from watching for changes during local development
watch = true

[permalinks]
  posts = "/:title/"

#CUSTOM PARAMS
[params]
  ## Any stylesheet added here will come in *after* the theme stylesheet
  ## To override or add styles, put just the filenames here and put the actual stylesheets in static/assets/css in your source
  custom_css = []
  sitesubtitle = ""
  # These keywords will be added whenever "keywords: XXXX" are not available in a single content item
  sitekeywords = "your,default,keywords,for,this,site"
  ## organizationname is needed for structured data for SEO (ie, json+ld); see layouts/partials/
  organizationname = "Your Organization Name"
  ## Only CopyrightYear if auto-generated year based on last publish date is no longer working
  copyrightyear = ""
  sitedescription = "The default description of your site set in config.toml"
  ## Add GA Tracking Code Here. This leverages a built-in (ie, "internal") partial from HUGO: https://gohugo.io/extras/analytics#configuring-google-analytics
  googleanalyticstrackingcode = ""
  ## Twitter handle without the "@"
  twitterhandle = "yourtwitterhandle"
  ## Facebook URL
  facebook = "https://www.facebook.com/example/"
  ## Default Image for Social Sharing. This image should live at static/images/; be sure to size this to at least 1200px wide and optimize it.
  defaultsocialimage = "your-default-social-image.jpg"
  ## Site Notifications - set to true and add title (required) and body copy
  addsitenotification = true
  ## Short bio description on homepage list (note: accepts markdown)
  sidebarbioheading = "Bio"
  sidebarbio = "Sidebar bio and defaultsidebarimage set in config"
  sidebardefaultimage = "default-sidebar-image.jpg"
  ## Setting this to true will add a "noindex" to *EVERY* page on the site and prevent it from being indexed by external search engines
  removefromexternalsearch = true
  ## Set to true to include a CDN call to FontAwesome; NOTE: this can also be set to "true" in _variables.scss and unhighlighted in styles.scss if you are comfortable using gulp-sass.
  usefontawesome = true
  ## Disqus Comments
  ### Once set to true, disqus comments will be included on *all* single pages; to remove from single pages, add removecomments: true to your front matter
  usedisqus = true
  ### Your unique disqus shortname is required if you include comments
  disqusshortname = "rdwattersthemes"

## Configuration for BlackFriday
[blackfriday]
  plainIDAnchors = true
  hrefTargetBlank = true
  angledQuotes = false
  latexDashes = true

[taxonomies]
  tag = "tags"
  category = "categories"
```

## Customizations

You can add custom design/style assets by creating new stylesheets.




[clipboard.js]: https://clipboardjs.com/
[Featherlight image modal]: http://noelboss.github.io/featherlight/
[freehtml5.co's Story theme]: https://freehtml5.co/story-free-html5-bootstrap-template-for-personal-blog-websites/
[official Gulp docs]: http://gulpjs.com/