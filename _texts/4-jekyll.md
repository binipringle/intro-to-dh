---
layout: narrative
title: Introduction to Jekyll
author: Patrick Smyth
editor: Sabina Pringle
source: CUNY Graduate Center Digital Research Institute
rights: Introduction to Jekyll is licensed under a Creative Commons Attribution-ShareAlike 4.0 International License. Introduction to Jekyll is based on Introduction to Jekyll of the Digital Research Institute (DRI) Curriculum by Graduate Center Digital Initiatives (GCDI) at https://github.com/DHRI-Curriculum. When sharing this material or derivative works, preserve this paragraph, changing only the title of the derivative work, or provide comparable attribution.
source: Graduate Center Digital Humanities Research Institute
toc:
- Interacting with Python
- Types
- Variables
- Running scripts
- Errors in Python

---

#### This session was adapted from previous work by Patrick Smyth for the CUNY Graduate Center Digital Research Institute (GC DRI).

---

Static site generators provide a way to build a website that has modern functionality—blogging, RSS, templating, markdown—without the overhead of a database. While certain features, such as comment sections, are difficult to implement on a static site, static sites have many advantages: they are more maintainable, simpler to understand and modify, are difficult to hack, and are more archivable and sustainable. They also fit neatly into a content management workflow that includes the command line, a text editor, Git, and markdown.

In this session, we will use Jekyll, a popular static site generator written in the Ruby programming language, to build and modify a version of our Digital Research Institute website. In doing so, we'll learn about templates, including layouts and includes, and also how to host your static site on GitHub Pages.

# What Is a Static Site?

## What's Old Is New Again

In the beginning, there was HTML. Web pages were documents that connected to other documents, and were created by hand-writing HTML.

In the 2000s, a broad trend toward dynamic websites began. Rather than a collection of documents, these websites consisted of template documents backed up by a database. When a user requested a page, the appropriate template would be chosen, the database would be consulted, and the page would be built on the fly and served to the user. WordPress is a well-known example of this dynamic model, but other content management systems such as Drupal as well as proprietary services such as Squarespace and Twitter also use a database-backed dynamic model.

In the mid-2010s, a new paradigm for website creation, the static site generator, began seeing widespread use. Rather than build individual pages at the moment they are requested by the user, these sites take folders of content, often in markdown, and use templates to generate a complete website. The output of this process is then hosted as static HTML files. Static sites are cheaper to host, expose a smaller surface area to hackers, and tend to have more comprehensible internals than comparable dynamic sites. Though static sites are a favorite of technical bloggers, companies like MailChimp and Vox Media have begun to use them to host their primary websites.

## Advantages and Disadvantages

Advantages of static sites:

- Load faster and are cheaper to host.
- Difficult to hack.
- More comprehensible internals.
- Easy to put under version control.
- Can be hosted on any computer/server/host configuration.
- Are often free to host on sites like GitHub, Netlify, or GitLab.
- Require no updates and are less likely to break over time.

Disadvantages of static sites:

- Features dependent on user input, such as comments or "Most popular" widgets, are not possible or require workarounds.
- Non-technical users have a more difficult time contributing content—no WordPress-style admin panel.
- Can be slow to build a large or very large site.

---


# Installation

## Windows

Note that Jekyll does not officully support Windows. But it still works.

1. Download the latest version of (RubyInstaller for Windows)[https://rubyinstaller.org/downloads/]. This should be the first item under the heading "WITH DEVKIT."
2. Run the executable installer. Use default options.
3. At installation completion, leave the box checked that allows installation to the command line.
4. When closing the installer, a command line should appear with a menu prompt. Type `1` and press `Enter`.
5. Once the menu appears again, press `Enter` to close it.
6. Click the Start menu or press the Windows button on your keyboard (the button near Control).
7. Type `cmd` and press `Enter`.
8. At the command line, type these commands:

```
gem install jekyll
gem install bundler
```

At this point, Jekyll should be installed and available. You can type `jekyll --version` to confirm that it's available to you.

## Mac OS

### First things first: Homebrew

To install Jekyll, you'll first need Ruby. And to install Ruby, you'll first need Homebrew.

Open your terminal by clicking the magnifying glass in the top right of your desktop and typing `terminal` in the bar that appears. Terminal should be the first application that appears.

Enter the following:

```sh
xcode-select --install
```

You may need to agree to a terms and conditions window that appears.

After the installation above completes, enter the following to install Homebrew. (Make sure you don't omit the beginning or end of this command.)

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Time to install Ruby

You should now be able to run the following command in your command line in order to install Ruby:

```sh
brew install ruby
```

Once the install finishes, you can test that the ruby install worked by running the following command:

```sh
which ruby
```

The response should be the path to the ruby installation on your computer. If you run into any troubles in the last steps above, try adding the path to your shell configuration by running:

```sh
export PATH=/usr/local/opt/ruby/bin:$PATH
```

If you have any trouble with the install beyond what is covered here, the Jekyll website provides some great [Troubleshooting advice](https://jekyllrb.com/docs/troubleshooting/)

### Finally, Jekyll!

Now we are ready to install Jekyll, which is easily accomplished by running the following command in your terminal:

```sh
gem install bundler jekyll
```

That should be it! We're ready to go. If you want to double check whether Jekyll is installed, run the following command:

```sh
jekyll -v
```

It should provide you with the version number of the local Jekyll installation.

---

# Getting Started: Setting Up A First Website

Now we are ready to get our first site set up and running. In order to do so, we need to create a new site. You can create a site inside an already existing folder but in the following, we'll set up a clean site using Jekyll's own generator.

## Decide Location

First, you need to decide where your site should live locally. In order to navigate to the Desktop folder of your user account, run this command in your command line:

```console
cd ~/Desktop
```

_In our example, we'll put the site on your computer's desktop but you may want to navigate to a different directory. You can do this by using `cd` as you may remember from our [command line workshop](http://www.github.com/DHRI-Curriculum/command-line)._

We will create a new Jekyll site on the desktop by writing:

```console
jekyll new my-site
```

This command may take some time to run, so take a break—stand up and stretch your arms—while it runs. Once it is done, your command line should have an output that looks something like this:

```console
Running bundle install in ~/Desktop/my-site...
  Bundler: Fetching gem metadata from https://rubygems.org/...........
  Bundler: Fetching gem metadata from https://rubygems.org/.
  Bundler: Resolving dependencies...
  Bundler: Fetching public_suffix 3.0.3
  Bundler: Installing public_suffix 3.0.3
  Bundler: Fetching addressable 2.6.0
  Bundler: Installing addressable 2.6.0
  Bundler: Using bundler 2.0.1
  Bundler: Using colorator 1.1.0
  Bundler: Fetching concurrent-ruby 1.1.5
  Bundler: Installing concurrent-ruby 1.1.5
  Bundler: Fetching eventmachine 1.2.7
  Bundler: Installing eventmachine 1.2.7 with native extensions
  Bundler: Using http_parser.rb 0.6.0
  Bundler: Using em-websocket 0.5.1
  Bundler: Fetching ffi 1.10.0
  Bundler: Installing ffi 1.10.0 with native extensions
  Bundler: Using forwardable-extended 2.6.0
  Bundler: Using i18n 0.9.5
  Bundler: Using rb-fsevent 0.10.3
  Bundler: Fetching rb-inotify 0.10.0
  Bundler: Installing rb-inotify 0.10.0
  Bundler: Using sass-listen 4.0.0
  Bundler: Fetching sass 3.7.4
  Bundler: Installing sass 3.7.4
  Bundler: Using jekyll-sass-converter 1.5.2
  Bundler: Using ruby_dep 1.5.0
  Bundler: Using listen 3.1.5
  Bundler: Fetching jekyll-watch 2.2.1
  Bundler: Installing jekyll-watch 2.2.1
  Bundler: Fetching kramdown 1.17.0
  Bundler: Installing kramdown 1.17.0
  Bundler: Fetching liquid 4.0.3
  Bundler: Installing liquid 4.0.3
  Bundler: Using mercenary 0.3.6
  Bundler: Fetching pathutil 0.16.2
  Bundler: Installing pathutil 0.16.2
  Bundler: Fetching rouge 3.3.0
  Bundler: Installing rouge 3.3.0
  Bundler: Fetching safe_yaml 1.0.5
  Bundler: Installing safe_yaml 1.0.5
  Bundler: Using jekyll 3.8.5
  Bundler: Fetching jekyll-feed 0.12.1
  Bundler: Installing jekyll-feed 0.12.1
  Bundler: Fetching jekyll-seo-tag 2.6.0
  Bundler: Installing jekyll-seo-tag 2.6.0
  Bundler: Fetching minima 2.5.0
  Bundler: Installing minima 2.5.0
  Bundler: Bundle complete! 4 Gemfile dependencies, 29 gems now installed.
  Bundler: Use `bundle info [gemname]` to see where a bundled gem is installed.
  Bundler: Post-install message from sass:
  Bundler:
  Bundler: Ruby Sass has reached end-of-life and should no longer be used.
  Bundler:
  Bundler: * If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  Bundler: primary implementation: https://sass-lang.com/install
  Bundler:
  Bundler: * If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  Bundler: sassc gem: https://github.com/sass/sassc-ruby#readme
  Bundler:
  Bundler: * For more details, please refer to the Sass blog:
  Bundler: https://sass-lang.com/blog/posts/7828841The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
New jekyll site installed in ~/Desktop/my-site.
```


## Serve the Server

We are now ready to navigate into our new site directory using the change directory command `cd`:

```console
cd my-site
```

Once inside the directory, we will build the site and make it available to us. Jekyll provides a command which you will use _a lot_ if you work with the generator (write it down on a notepad next to you!):

```console
bundle exec jekyll serve
```

Once you run this command, Jekyll will start up a local server, which you can navigate to in your web browser by going to http://localhost:4000/.


## Your First Site

The first site that Jekyll has generated looks something like this:

![Image showing a first, blank website, with a lot of occurrences of the word "awesome" in different places](images/blank-site.png)

A lot of "awesome" and too little content.


## The Backend of Your First Site

If you use the GUI interface on your computer (Finder on a Mac and Explorer on a PC) and navigate to the directory where we set up the site, you will see that it contains a number of files:

![Image showing a list of all the sites in the directory where the first site was set up.](images/blank-site-directory.png)

This is what is called the "backend" of your site. For now, we will not care too much about the files but we will look more in-depth at some of them in the next couple of pages in this workshop.

For now, you can just peek into the folder called `_site` and see that Jekyll has automatically generated content in this folder, which can be uploaded to any server anywhere and that will look exactly the same everywhere. Jekyll uses these files for the local server that is located at http://localhost:4000/.


## Exiting

In the next couple of pages, we will work more in-depth with a site to understand Jekyll's structure and formatting but this is the simple way to set up a site based on blog posts.

For now, let's go back to the command line where you should still see the server running:

```console
Configuration file: ~/Desktop/my-site/_config.yml
            Source: ~/Desktop/my-site
       Destination: ~/Desktop/my-site/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
       Jekyll Feed: Generating feed for posts
                    done in 0.891 seconds.
 Auto-regeneration: enabled for '~/Desktop/my-site'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

Hold down the `ctrl` key on your keyboard and press `c` simultaneously. The server should shut down and you should be back at a `$` prompt.
