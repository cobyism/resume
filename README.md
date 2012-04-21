# Chassis

This is far from ready/usable at the moment, so bear with me. **Presume nothing works**.

## What is Chassis?

Chassis is an open-source web development framework. It's a way to quickly get up and running with tools that make your life easier as a web developer.

For keeping you sane while developing, Chassis lets you write:
- HTML using [HAML](http://haml-lang.com/).
- CSS using [Sass](http://sass-lang.com/).
- Javascript using [CoffeeScript](http://coffeescript.org/).

## Installation

```sh
$ git clone git://github.com/cobychapple/chassis.git
$ cd chassis
```

## Usage

```sh
$ rake watch
>>> Watching for changes
```

Press `Ctrl-C` to kill `rake watch`.

## More Information

### How does it work?

Simply put, Chassis gives you two directories:
- A `source` directory, in which you put all your HAML, Sass, and CoffeeScript files, and any other files that make up your site.
- A `public` directory, which will be a mirror image of the `source` directory, except with the compiled versions of the HAML, Sass, and CoffeeScript files.

Any time you make a change to a HAML, Sass, or CoffeeScript file in the source. Any other files (e.g. images, PDFs) in the `source` directory will simply be mirrored across to the `public` directory without modification.

### Isn't this what Compass does?

Some people will probably just say "Why not just use [Compass](http://compass-style.org/)? Here's my answer:
- Compass doesn't let you write HTML in HAML. Chassis does.
- Compass feels like it does too much magic. Chassis just compiles and leaves everything else alone.
- Compass is far more polished than this will probably ever be. Chassis is partly a coding excercise for me.

Use whatever works for you.

### How this will eventually work

Eventually I'd say I'll turn this into a gem, so here's how stuff will work some time in the future.

#### Install

```sh
$ gem install chassis
```

#### Usage

```sh
$ chassis create /my/new/project
$ cd /my/new/project
```

Then use either:

```sh
$ chassis watch
>>> Watching for changes
```

or:

```sh
$ chassis generate
>>> Generating compiled output
```

#### Features it'll eventually have

- A generic, yet beautiful UI that should suit almost project or site with minimal changes.
- A responsive grid framework, with fluid images and lots of media-queryish-goodness.
- Plenty of neat widgets and design patterns that are easy to setup and use with minimal code.
- Easily create and share your own themes that override the default UI.
- Javascript goodies like sticky navigation bars, sidebars that float with the viewport as you scroll, but don't go past the end of their container element, and such.
- Maybe a set of common web icons to go with the buttons and stuff.
- Plenty of web-font stacks rearing to go.
- A set of nice, subtle background patterns and textures built in.

#### Working with other tools and frameworks

*Eventually* Chassis will also let you work with a few of the popular CSS frameworks, such as:
- [Bootstrap](http://twitter.github.com/bootstrap/), by [Twitter](http://twitter.com)
- [Foundation](http://foundation.zurb.com/), by [Zurb](http://www.zurb.com/)
- [960.gs](http://960.gs/)
- [978.gs](http://978.gs/)
- [Golden Grid System](http://goldengridsystem.com/)
- [Less Framework](http://lessframework.com/) (not to be confused with [LESS CSS](http://lesscss.org/))
- [Fluid Baseline Grid](http://fluidbaselinegrid.com/)

It will also incorporate some other practices/snippets made popular by the above, as well as:
- [Normalize.css](http://necolas.github.com/normalize.css/)
- [HTML5 Boilerplate](http://html5boilerplate.com/)


#### To-do

- Convert the whole thing to an installable gem
- Add a `rake generate` task for single-use compilation.
- Modify `rake watch` so that it does an initial check over everything when first run.
- Make it so people can use popular CSS frameworks/grids, possibly with namespaced CSS styles (like .bootstrap, .zurb, .960-grid, .978-grid etc).
- Hook it all up to a GitHub pages domain.
- Maybe add an easy shell-script installer (pow.cx style)? For example: `curl cobychapple.github.com/get-chassis | sh && rake watch` (probably not needed if it's eventually converted to a gem).
- Much, much more.

## License

Copyright 2011 Coby Chapple.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
