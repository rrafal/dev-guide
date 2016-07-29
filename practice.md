
# Development in Practice

## Frontend

Use [Bower](https://bower.io/) package manager for most front-end libraries
(JS, CSS, images, etc.). [Configure](https://bower.io/docs/config/) its `directory`
option to point to appropriate folder.

Use Gulp to process your assets. You can compile CSS and JS, optimize code, add browser
prefixes to CSS, lint, compress and organize files, etc. You can also create Gulp task
to run local web server. See [gulp-connect-php](https://www.npmjs.com/package/gulp-connect-php)
as an example.

Contacts Forms:

* [Dropifi](http://www.dropifi.com/)
* [JotForm](https://www.jotform.com)

Frameworks

* [Bootstrap](http://getbootstrap.com/)
* [Foundation](http://foundation.zurb.com/)

Graphcs:

* [Font Awesome](http://fontawesome.io/icons/)
* [IcoMoon](https://icomoon.io/)

Tours:
* [Guiders](https://github.com/jeff-optimizely/Guiders-JS)
* [JimmyBonney](http://jimmybonney.com/articles/8_welcome_tours_web_applications/)
* [JQuery from CodeRops](http://tympanus.net/codrops/2010/12/21/website-tour/)
* [Jquery Joyride 2](http://zurb.com/playground/jquery-joyride-feature-tour-plugin)

## CSS

Pick a set of conventions for all your class names. Keep number of rules to minimum.
Some ideas:

* use short prefix, ex. acronym of the company
* use 2-3 words
* `-button` suffix for buttons, ex. `close-button`
* `-input` suffix for inputs, ex. `name-input`
* `-heading` for `h1`-`h6`, ex. `large-heading`
* `website-` suffix for header and footer, ex: `website-logo`
* `-container` suffix for reusable elements, ex: `news-container`
* single adjective for boolean properties, ex: `active`
* `-style` suffix for style variations, ex: `green-style`

Show element hierarchy in class names. For example, use the same prefix `message-` for all ements
in a container:

```HTML
<div class="message-container warning-style">
  <h1 class="message-heading">Sorry...</h1>
  <p class="message-body">This product is no longer available.</p>
</div>
```

## Python

Frameworks:
* [Flask](http://flask.pocoo.org/)
* [Django](https://www.djangoproject.com/)

Libraries:
* [pip](https://pip.pypa.io/en/stable/) - Python Package Manager
* [Requests](http://docs.python-requests.org/en/master/) - HTTP for Humans
  * Always use timeout

## Deployment

Linux:

* Set server to UTC timezone.
* Synchronising time: `sudo apt-get install ntp; ntpdate -s ntp.ubuntu.com;`
* Set MTU to 1500 (http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/network_mtu.html)

Hosting:

* aws.amazon.com
* godaddy.com
* rackspace.com 
* digitalocean.com  $60 / year
* namecheap.com $210 / year

Domain:

* domains.google.com

SSL:

* letsencrypt.org
