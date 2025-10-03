# Getting Started

Getting up and running with Semantic UI

## Preface

#### Using Build Tools

Semantic UI packaged Gulp build tools so your project can preserve its [own theme changes](/usage/theming.html).

The easiest way to install Semantic UI is our NPM package which contains special install scripts to make setup interactive and updates seamless.

For installing with specific integrations like Ember, React, or Meteor, see our [integration guide](/introduction/integrations.html)

For integrating Semantic UI tasks into your own build tools, or using a CDN see our [recipes](/introduction/advanced-usage.html) section.

> <div class="ui header">Simpler Setup</div>
> <p>If you are using Semantic UI as a dependency and just want to use our default theme, use our lighter [semantic-ui-css](https://github.com/Semantic-Org/Semantic-UI-CSS) or [semantic-ui-less](https://github.com/Semantic-Org/Semantic-UI-Less) repo. If you just need the files you can download them as a zip from GitHub.</p>
> [Download Zip](https://github.com/Semantic-Org/Semantic-UI-CSS/archive/master.zip)
> [View all Semantic-Org Repos](https://github.com/Semantic-Org/)

## Installing

#### Install NodeJS
If you are unfamiliar with setting up NodeJS you can follow the steps below, or check out the [download page](https://nodejs.org/download/) on [nodejs.org](http://www.nodejs.org)

### Mac

#### Option 1: Homebrew
After installing [homebrew](http://brew.sh/)
```bash
brew install node
```

#### Option 2: Git
```bash
git clone git://github.com/nodejs/node.git
cd node
./configure
make
sudo make install
```

### Linux

#### Install via PPA
Although [Chris Lea's PPA](http://www.ubuntuupdates.org/ppa/chris_lea_nodejs) was once the best way to install node, it is now somewhat out of date.

The recommended path to install Semantic UI is using [Joyent's package manager](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager) guide.

#### Ubuntu
```bash
curl --silent --location https://deb.nodesource.com/setup_6.x | sudo bash -
sudo apt-get install --yes nodejs
```

#### Debian
```bash
apt-get install curl
curl --silent --location https://deb.nodesource.com/setup_6.x | bash -
apt-get install --yes nodejs
```

#### Red Hat
```bash
curl --silent --location https://rpm.nodesource.com/setup | bash -
yum -y install nodejs
```

### Windows

#### Install the exe
Download the [NodeJS executable](http://nodejs.org/download/).

#### Install Gulp
Semantic UI uses [Gulp](http://www.gulpjs.com) to provide command line tools for building themed versions of the library with just the components you need.

Gulp is an NPM module and must be installed globally
```bash
npm install -g gulp
```

#### Install Semantic UI
Semantic UI is available in an eponymous package on NPM

### Video
```html
<script type="text/javascript" src="https://asciinema.org/a/22121.js" id="asciicast-22121" async></script>
```

### Code
```bash
npm install semantic-ui --save
cd semantic/
gulp build
```

#### Include in Your HTML
Running the gulp build tools will compile CSS and Javascript for use in your project. Just link to these files in your HTML along with the latest [jQuery](http://www.jquery.com).
```html
<link rel="stylesheet" type="text/css" href="semantic/dist/semantic.min.css">
<script
  src="https://code.jquery.com/jquery-3.1.1.min.js"
  integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
  crossorigin="anonymous"></script>
<script src="semantic/dist/semantic.min.js"></script>
```

## Updating

#### Updating via NPM
Semantic's NPM install script will automatically update Semantic UI to the latest version while preserving your site and packaged themes.
```bash
npm update
```

## Next Steps

#### All Set!
Well done! Semantic UI is now ready to be used.

```html
<div class="three column divided stackable center aligned ui grid">
  <div class="column">
    <div class="ui icon header">
      <i class="rocket circular icon"></i>
      See how to use <a href="/introduction/build-tools.html">gulp commands</a> and build tools
    </div>
  </div>
  <div class="column">
    <div class="ui icon header">
      <i class="theme circular icon"></i>
      Learn about <a href="/usage/theming.html">changing themes</a>
    </div>
  </div>
  <div class="column">
    <div class="ui icon header">
      <i class="food circular icon"></i>
      See <a href="/introduction/advanced-usage.html">recipes</a> for using Semantic UI in your project
    </div>
  </div>
</div>
```
