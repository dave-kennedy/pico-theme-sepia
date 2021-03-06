# Sepia Theme for Pico CMS

> Depending on your server, you might need to run the following commands with elevated permissions.

> In each of the following commands, replace DIR with the location of your themes directory, e.g.
> `/var/www/localhost/htdocs/pico/themes`.

> Skip ahead for instructions pertaining to the Nextcloud integration.

## Install

Run this command inside this directory:

    $ setup.sh install DIR

Replace DIR with the location of your themes directory.

Finally, change the theme in your `config.yml` to `sepia`.

## Update

The same command used to install the theme can be used to update it.

## Uninstall

Run this command inside this directory:

    $ setup.sh uninstall DIR

Replace DIR with the location of your themes directory.

Don't forget to change the theme in your `config.yml`.

## Blog support

If you want to add a list of blog posts to your page, use the `blog-index` template, e.g.:

    ---
    Title: Welcome
    Description: A list of blog posts by me.
    Author: Joe Bloggs
    Date: 2021-10-24
    Template: blog-index
    ---

Blog posts get their own template, and can have one or more `Tags`:

    ---
    Title: My First Post
    Description: This is my first blog post ever. Be nice.
    Author: Joe Bloggs
    Date: 2021-10-25
    Template: blog-post
    Tags:
        - Foo
        - Bar
    ---

Finally, make sure the following values in `pico-theme.yml` are correct:

    blog_index_id: blog/index
    blog_posts_dir: blog/posts

## Navigation

To display a navigation menu beneath the header, create a file named `_navigation.md` in your
content folder. This file should contain a `Links` meta attribute, the value of which should be a
mapping of page titles to IDs, e.g.:

    ---
    Links:
        Blog: blog
        About: about
        Contact: contact
    ---

## Nextcloud

These instructions pertain only to the Nextcloud integration.

> In each of the following commands, replace DIR with the location of your themes directory, e.g.
> `/var/nextcloud/data/appdata_asdf1234/cms_pico/themes`.

### Install

1. Run this command inside this directory:

       $ sudo -u www-data setup.sh install DIR

2. In Nextcloud settings, go to Administration > Pico CMS and scroll down to the section labeled
   "Custom themes". Select "sepia" from the dropdown menu and press the plus sign.

3. Still in Nextcloud settings, go to Personal > Pico CMS and select "sepia" from the dropdown menu
   next to the name of your site.

### Update

1. Run this command inside this directory:

       $ sudo -u www-data setup.sh install DIR

2. In Nextcloud settings, go to Administration > Pico CMS and scroll down to the section labeled
   "Custom themes". Press the "Reload custom theme" button next to "sepia".

### Uninstall

1. Run this command inside this directory:

       $ sudo -u www-data setup.sh uninstall DIR

2. In Nextcloud settings, go to Administration > Pico CMS and scroll down to the section labeled
   "Custom themes". Press the "Delete custom theme" button next to "sepia".

3. Still in Nextcloud settings, go to Personal > Pico CMS and select another theme from the dropdown
   menu next to the name of your site.

