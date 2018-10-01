
# Lektor Themes

A collection of all themes that were created by the Lektor community.

# Installation

## Installing all themes

If you would like to install all of the available Lektor themes, simply clone the entire repository from within your project directory with this command:

    git clone --depth 1 --recursive https://github.com/lektor/lektor-themes.git themes

## Installing a single theme (*nix instructions)

```bash
mkdir themes
cd themes
git clone URL_TO_THEME
```

or installing into an existing repository (for a Lektor project):

```bash
mkdir themes
cd themes
git submodule add URL_TO_THEME
```

# Adding a theme to the list

* Create your theme.
* Add a descriptive `README.md` to the root of the theme;
* Open up a new Issue with a link to the theme's repository on GitHub.

We encourage theme authors to supply a self-contained Lektor site in `/example-site` to easily illustrate their theme. Please make the site's content as neutral as possible. We further encourage you to use this example site to produce screenshots (placed in `/images`) that we can use to add this theme to a showcase on [getlektor.com](https://getlektor.com).

**NOTE:** The folder name here is important, as this folder will be picked up and used to generate the a list of themes on getlektor.com.

Each theme needs:

1. To be added to the lektor-themes repo;
1. A good README.md;
1. A good `theme.ini`

Additionally, each theme is strongly encouraged to include:

1. an `example-site` that is fully functional in-place with just `lektor server`.<sup>1</sup>
1. screenshots in `/images/`

[1] Making your example-site fully functional and DRY is a bit tricky, but it can be accomplished with the creation of a single symlink. Go into the example-site's `themes` dir, and run `ln -s ../../../[theme repo dir]/ [theme repo dir]`. Note the lack of a trailing `/`.

## theme.ini

This file contains metadata about the theme and its creator. **Only `theme.ini` is accepted, not `theme.yaml`, `theme.json`, or `theme.toml`**. The following fields are required:

```ini
[theme]
name = Nix
license = MIT
licenselink = https://github.com/rlaverde/lektor-theme-nix/blob/master/LICENSE.md
description = Simple, minimal theme for Lektor
homepage = https://github.com/rlaverde/lektor-theme-nix
tags = simple, minimal, unix, terminal, blog
features = blog
lektor_required_version = 3.1

[author]
name = rlaverde
homepage = http://rlaverde.github.io/

# If porting an existing theme
[original]
author = Matúš Námešný
homepage = https://namesny.com
repo = https://github.com/LordMathis/hugo-theme-nix
```

## README.md

Your theme's README file
(which should be written in Markdown and called `README.md`)
serves a double purpose.
This is because its content will appear in two places&mdash;i.e., it will appear:

1. On your theme's details page on getlektor.com; and
1. At GitHub (as usual), on your theme's regular main page.

**Note:** If you add screenshots to the README please make use of absolute file paths instead of relative ones like `/images/screenshot.png`. Relative paths work great on GitHub but they don't correspond to the directory structure of getlektor.com. Therefore, browsers will not be able to display screenshots on the theme site under the given (relative) path.
