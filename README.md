Hacker Space Website
====================

This is static website hosted in http://chautari-space.github.io. It is generated using hugo

## How to contribute

### [Hugo](http://gohugo.io/)

Hugo is a general-purpose website framework, static site generator, similar to jekyll. It flexibly works with many formats and is ideal for blogs, docs, portfolios and much more. It is written for speed and performance.

Hugo is a static site generator like jekyll.
### Installing Hugo

  - Archlinux

  ```sh
    $ yaourt -S hugo-git
  ```

  - Other linux

    ```sh
      $ # hugo can be installed either using gem or npm
      $ ## if using ruby gem
      $ gem install hugo
      $ ## or you can use npm
      $ npm install -g hugo
    ```

  - Installing hugo from source

    Follow the guide in http://exponential.io/blog/2015/02/25/install-hugo-on-ubuntu-linux/

### Set up the site
  - Clone the source branch and create folders

  ```sh
    $ cd /path/to/projects
    $ # clone the source branch
    $ git clone https://github.com/chautari-space/chautari-space.github.io.git -b source
    $ cd chautari-space.github.io
    $ # make directories required by hugo
    $ mkdir -p archetypes content data layouts public static
  ```

### Modify the site

To make changes in the contents or details modify ```sh config.toml```

To modify the front end look and feel (html, css, layout, javascripts) modify the themes/hugo-agency-theme. The layout is located in themes/hugo-agency-theme/layouts/. Similary, css in themes/hugo-agency-theme/static/css and javascripts in themes/hugo-agency-theme/static/js.

### View and Deploy the changes

Preview the changes by opening a localhost at 1313 port using the command.

  ```sh
    $ hugo server -w --theme=hugo-agency-theme --buildDrafts
  ```

Generate the final static site using

  ```sh
    $ hugo --theme=hugo-agency-theme
  ```

Deploy the generated site to github

  ```sh
    $ # stay in source branch
    $ git checkout source
    $ # add the changes
    $ git add .
    $ # commit the changes
    $ git commit -m "commit message"
    $ # push only generated files in public directory to master branch
    $ git subtree push --prefix public origin master
  ```