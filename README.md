### Santeri's Github Workflow status badges

![Deploy Theme](https://github.com/iamsanteri/casper-lostbookofsales/workflows/Deploy%20Theme/badge.svg)

![Test](https://github.com/iamsanteri/casper-lostbookofsales/workflows/Test/badge.svg)

# [16-03-2021] IMPORTANT UPDATE: 

Since Ghost version 4.0, as well as the latest updates to the the Casper theme, there are now too many changes in the original source to merge and resolve conflicts with the LBS fork. 

There are so many conflicts and changes based on the custom additions to this theme, that we need to fully branch off from the upstream source and remain as-is. Only custom changes without merging the upstream should be processed. 

For a next big jump and refresh, start working off from a complete custom template.  

# Santeri's notes: 

### Read update above before proceeding. 

1. Fetch and merge latest official changes from the original repo
2. Resolve possible conflicts, add modfifications
3. Push changes to remote. Note that the remote changes will be automatically pushed to the live blog instance due to a custom integration. 

Read more about the custom integration here: https://ghost.org/integrations/github/

Update, no longer relevant: ~~To avoid missing out on future updates to the default Casper theme, keep your fork up to date (don't forget to commit your changes first)~~.

    cd into/cloned/fork-repo
    git remote add upstream git://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git - Example below. 
    EXAMPLE: git remote add upstream https://github.com/TryGhost/Casper.git
    git fetch upstream
    git pull upstream master - Branch changed to main from "master"
    git push

Article: https://grantwinney.com/how-to-customize-the-default-casper-theme-in-ghost/

# Santeri's notes for modifying the AMP templates

Motivation: https://www.syncwithtech.org/amp-template-ghost/

### Consider disabling AMP temporarily 

- Consider customizing like mentioned here: https://www.syncwithtech.org/amp-template-ghost/
- Remember to include a Google Analytics script! More information on Ghost AMP templates in Ghost docs here: https://ghost.org/tutorials/custom-amp-themes-2/
- Try to include a Mailchimp email conversion form in the AMP template for a post. Read more here: https://amp.dev/documentation/components/amp-form/
- Remember to validate your template by adding /amp/#development=1 to the URL. This will not only render your AMP template, but also open the AMP validator.
- Test the signup and conversion flow
- Test visibility in Google Analytics. 

## Consider adding a cookie statement

- If needed

Standard Readme continues onwards from here: 

# Casper

The default theme for [Ghost](http://github.com/tryghost/ghost/). This is the latest development version of Casper! If you're just looking to download the latest release, head over to the [releases](https://github.com/TryGhost/Casper/releases) page.

&nbsp;

![screenshot-desktop](https://user-images.githubusercontent.com/353959/66987533-40eae100-f0c1-11e9-822e-cbaf38fb8e3f.png)

&nbsp;

# First time using a Ghost theme?

Ghost uses a simple templating language called [Handlebars](http://handlebarsjs.com/) for its themes.

This theme has lots of code comments to help explain what's going on just by reading the code. Once you feel comfortable with how everything works, we also have full [theme API documentation](https://ghost.org/docs/themes/) which explains every possible Handlebars helper and template.

**The main files are:**

- `default.hbs` - The parent template file, which includes your global header/footer
- `index.hbs` - The main template to generate a list of posts, usually the home page
- `post.hbs` - The template used to render individual posts
- `page.hbs` - Used for individual pages
- `tag.hbs` - Used for tag archives, eg. "all posts tagged with `news`"
- `author.hbs` - Used for author archives, eg. "all posts written by Jamie"

One neat trick is that you can also create custom one-off templates by adding the slug of a page to a template file. For example:

- `page-about.hbs` - Custom template for an `/about/` page
- `tag-news.hbs` - Custom template for `/tag/news/` archive
- `author-ali.hbs` - Custom template for `/author/ali/` archive


# Development

Casper styles are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and [Gulp](https://gulpjs.com) installed globally. After that, from the theme's root directory:

```bash
# install dependencies
yarn install

# run development server
yarn dev
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
# create .zip file
yarn zip
```

# PostCSS Features Used

- Autoprefixer - Don't worry about writing browser prefixes of any kind, it's all done automatically with support for the latest 2 major versions of every browser.
- [Color Mod](https://github.com/jonathantneal/postcss-color-mod-function)


# SVG Icons

Casper uses inline SVG icons, included via Handlebars partials. You can find all icons inside `/partials/icons`. To use an icon just include the name of the relevant file, eg. To include the SVG icon in `/partials/icons/rss.hbs` - use `{{> "icons/rss"}}`.

You can add your own SVG icons in the same manner.


# Copyright & License

Copyright (c) 2013-2021 Ghost Foundation - Released under the [MIT license](LICENSE).
