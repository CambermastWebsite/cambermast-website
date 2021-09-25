# cambermast-website
This is the git repo using GitHub Pages and Jekyll for the [cambermast.com](https://cambermast.com) and [agileinaction.com](agileinaction.com) websites.

This code is free to use, although attribution would be nice. The only code you may *not* use is any content I create, such as blog posts, podcast posts, or other content directly tied to me (Bill Raymond), CAMBERMAST LLC or AgileInAction.com.

You are welcome to clone, send pull requests, or submit issues. This is a site for my company first, so it is not a public theme. Changes you request may be declined based on my own business priorites.

This is a Jekyll site designed for GitHub Pages. It was originally based on the Jekyll Minima theme, but I have since removed all (nearly all?) of that code and replaced it with my own.

## Features
* 100% of the site uses CSS Grid
* Tested on Chrome, Safari, Edge, Edge Chromium, and a little IE
* Fully responsive
* Practically no Javascript
* Uses a font mix-in to enable for maximum and minimum font sizes
* Data-driven menu system
* Designed to easily display various types of content (posts, podcasts) in a unique way with only one file
* GitHub action (workflow) that can force trigger the github-pages environment deployment and re-build the site.

## Home
/index.markdown is the jumping off point for the site.

## Workflow
For more information, see the [workflow readme file](https://www.cambermast.com/workflow-docs/readme).

## Blog and Podcast feeds
What makes this site unique is there are two types of posts (and more can be dynamically added):

* Blog posts
* Podcast posts

Both types are included in the _posts folder. They are made unique by the use of categories. When you go to __/includes/feed.html__, you will find that this file displays either types of posts. It will display a featured image in large or small versions. The large and small image can be different and you manage them in the __data/configs.yml__ file.

There in the __sass__ folder, you will find unique scss __feed__ files that will make the feed look vastly different. For example, the "feed" could show a wide-screen featured image with a gradient overlay and text, where the "feed" could also display as a list with small featured images to the left.

In other words, most of the content you see on the pages (featured podcast, featured blog, list of podcasts, lists of blogs), all display using the one __includes/feed.html__ file, all managed through scss.

Note that the __feed.scss__ file is the most important in that it sets the baseline for the grid layout. The additional SCSS files with a __feed__ prefix are modifiers to __feed.scss__ or unique to the type of feed display you want to display.

## How the feed displays differently
First, there is a calling page, like blog.markdown or podcast.markdown. Second, there is a layout file that uses a Liquid Include. In that Include are properties that pass to the feed.html file. It can change the whole section heading's CSS Class, so you can create a unique SCSS file that displays the content as you like. Remember there is a _feed.scss_ file that is a sort of main starting off point for styles.

The Liquid include also sends other properties to the feed.html file, such as what the default featured image should be (if one is not provided), how many posts to display, what the offset is for the post, and so on. You can place multiple feed.html files on a single page and they can all look different.
