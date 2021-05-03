use below steps - Reference

1.https://github.com/vivmagarwal/patternlab-php-twig-gulp
2. git clone https://github.com/vivmagarwal/patternlab-php-twig-gulp.git

-- go in folder of patternlab
- need to remove package-lock.json 
- npm install
-- composer install
composer require
- npm install gulp


------------------------------

chmod -R 777 .

composer install

npm install gulp
npm install gulp-sass
npm install gulp-sass-glob

gulp sass
php core/console --generate
php core/console --server --with-watch



npm rebuild gulp-sass


composer require .... --ignore-platform-reqs (if needed)
composer update

------------------------------
if not work
nvm use 10.16.0 
npm install 
composer install
--------------------------------

php core/console --generate
if having issue in composer install use this command 

composer update --ignore-platform-reqs  => and click on replace button
php core/console --server  => 
server started on http://localhost:8080 - use ctrl+c to exit...

if still facing this issue follow below steps
------------------------------------------------
steps

Patternlab PHP+Twig with Gulp task set up to watch and compile SCSS to CSS
Steps:
Pre Installation:
This setup required node version 10.x . I recommend using NVM for node version control : https://github.com/nvm-sh/nvm

To install or update nvm, you can use the install script using cURL:

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
or Wget:

wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
Useful nvm commands : nvm -h Show help nvm -ls Show list of node versions installed nvm install 10.16.0 Install this node version nvm use 10.16.0 Use this version of node

Installation:
nvm use 10.16.0 npm install composer install

Execution:
In first terminal tab: gulp watch In second terminal tab: php core/console --server --with-watch

Notes :
This setup is designed to keep all related files of a component together

Example:

--_patterns
  |--01-molecules
     |--primary-nav.twig
     |--primary-nav.scss
     |--primary-nav.js
     |--primary-nav.json
All the SCSS files inside source/_patterns is imported to scss/style.scss file. Then our gulp watch (gulp-sass) task compiles it to css/style.css. Then patternlabs php core/console --watch copies it to public/css

You dont need to manually import SCSS files inside atoms,molecules, organisms, templates and pages folder. all the scss files inside them will be included automatically.

But files inside common-scss/generic and common-scss/base must be imported manually in css/style.scss because in case of these files the order in which file is imported matters!!

All JS files inside source/_patterns are concatinated and imported to js/scripts.js file. Patternlab takes care of the rest.

license Packagist Gitter

Pattern Lab Standard Edition for Twig
The Standard Edition for Twig gives developers and designers a clean and stable base from which to develop a Twig-based pattern library.

Packaged Components
The Standard Edition for Twig comes with the following components:

pattern-lab/core: GitHub, Packagist
pattern-lab/patternengine-twig: documentation, GitHub, Packagist
pattern-lab/styleguidekit-assets-default: GitHub, Packagist
pattern-lab/styleguidekit-twig-default: GitHub, Packagist
Installing
There are two methods for downloading and installing the Standard Edition for Twig:

Download a pre-built project
Use Composer to create a project
Download a pre-built project
The fastest way to get started with the Standard Edition for Twig is to download the pre-built version from the releases page. The pre-built project comes with the Base StarterKit for Twig installed by default.

Please note: Pattern Lab uses Composer to manage project dependencies. To upgrade the Standard Edition for Twig or to install plug-ins you'll need to install Composer. We recommend that you install it globally.

Use Composer to create a project
Pattern Lab uses Composer to manage project dependencies.

1. Install Composer
Please follow the directions for installing Composer on the Composer website. We recommend you install it globally.

2. Install the Standard Edition for Twig
Use Composer's create-project command to install the Standard Edition for Twig into a location of your choosing. In Terminal type:

cd install/location/
composer create-project pattern-lab/edition-twig-standard your-project-name && cd $_
This will install the Standard Edition for Twig into a directory called your-project-name in install/location/. During the set-up process you will be asked to install an appropriate StarterKit. You will be automatically dropped into the project directory after the process is finished.

Updating Pattern Lab
To update Pattern Lab please refer to each component's GitHub repository. The components are listed at the top of the README.

Helpful Commands
These are some helpful commands you can use on the command line for working with Pattern Lab.

List all of the available commands
To list all available commands type:

php core/console --help
To list the options for a particular command type:

php core/console --help --[command]
Generate Pattern Lab
To generate the front-end for Pattern Lab type:

-------------------------------------------------------------
php core/console --generate
Watch for changes and re-generate Pattern Lab
To watch for changes and re-generate the front-end for Pattern Lab type:
-------------------------------------------------------------

-------------------------------------------------------------
php core/console --watch
Start a server to view Pattern Lab
You can use PHP's built-in web server to review your Pattern Lab project in a browser. In a seperate window type:
-------------------------------------------------------------

-------------------------------------------------------------
php core/console --server
Then open http://localhost:8080 in your browser.
-------------------------------------------------------------

Install a StarterKit
To install a near-empty StarterKit as a starting point for your project type:

php core/console --starterkit --init
To install a specific StarterKit from GitHub type:

php core/console --starterkit --install <starterkit-vendor/starterkit-name>


chmod -R 777 .

composer install

npm install gulp
npm install gulp-sass
npm install gulp-sass-glob

gulp sass
php core/console --generate




-------------------------------------------------------------------------

if need to add bem structure follow below things
---------------------------------

https://github.com/drupal-pattern-lab/bem-twig-extension

To use in Pattern Lab, simply place in the _twig-components/functions directory. Drupal needs to recognize the Twig function, so something like Unified Twig Extensions module can be helpful for that.


Usage (4 arguments)
Simple block name (required argument):
<h1 {{ bem('title') }}>

This creates:

<h1 class="title">

Block with modifiers (optional array allowing multiple modifiers):
<h1 {{ bem('title', ['small', 'red']) }}>

This creates:

<h1 class="title title--small title--red">

Element with modifiers and blockname (optional):
<h1 {{ bem('title', ['small', 'red'], 'card') }}>

This creates:

<h1 class="card__title card__title--small card__title--red">

Element with blockname, but no modifiers (optional):
<h1 {{ bem('title', '', 'card') }}>

This creates:

<h1 class="card__title">

Element with modifiers, blockname and extra classes (optional - in case you need non-BEM classes):
<h1 {{ bem('title', ['small', 'red'], 'card', ['js-click', 'something-else']) }}>

This creates:

<h1 class="card__title card__title--small card__title--red js-click something-else">

Element with extra classes only (optional):
<h1 {{ bem('title', '', '', ['js-click']) }}>

This creates:

<h1 class="title js-click">




---------------------------------------------------------------------------------------------------

How to use bem structure
https://www.fourkitchens.com/blog/design-ux/building-emulsify-part-2-callout-component/


<div {{ bem(portfolio_base_class, (portfoliowork_modifiers), portfolio_blockname) }}>
  <div {{ bem( 'mainwrap', (portfoliowork_modifiers), portfolio_base_class) }}>
  </div>
</div>