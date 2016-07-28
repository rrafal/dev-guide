# Web Development Guide

This is my another attempt at writing down best rules and practices in web software
development. This is not some theoretical discussion or rules for others.
Rather, it's a collection of best practices which a picked up over the years.

I did not invent any of the things I'm writing about. Either I stole them from people
who are smarter and better, or I discovered them the hard way - doing the same thing
over and over and learning along the way.

These rules are not a law which must be followed. Instead, they are best practicies which
I want to follow when it makes sense. They are practices relevent to what I work on,
to the tools and technologies I use, to the problems I solve. They might not work well,
or might not be applicable for other engineers. Also, they might become irrelevant for me
in a few year. Notherless, I think it's worth the time to write them down. First,
it might help others to understand who I am as a software engineer. Second, it will
remind me what rules I want to follow but do not necesserly do. Third, somebody might come
across this document and find it useful.

I'm writing this guide in markup so that I can turn it into a website. For the moment,
it will be just a set of markdown documents.

## Project

When you start working on a new project, make sure you understand the goal (expressed
in one sentence), requirements (functional and non-functional), stakeholders (all involved users),
expectations, current state, schedule, roadmap. Indentify issues which should be addressed
imediately, such as critical bugs, technical deb or high-risk areas. Make sure the product
owner has clear view of the project. For example, there should be a single list of known bugs
and needed featues.

Make sure there is a single list of all bugs and features. If you need additional documentation,
cross link with with docs in Google Drive. Write down more than might you need, especially:

* discussion notes
* pros and cons
* alternative ideas
* changes to feature

## Documentation

Vast majority of documentation should live in sourcecode in form of code comments. This
approach helps to have documentation which is:

* up to date
* close to where it's needed
* close to writer and reader (developer)
* versioned and with relevant code

Documentation should describe "why" and "what", not "how". Engineer can read how things
are done, but it's hard to guess why they are done that way.

In addition, there should be a set of documents that address general issues, not specific
to any part of the sourcode. This documentation can be kept in repo too, for example as
a README file. In other projects, it's easier to keep Google Drive folder. These auxiliary
documentation should include:

* quick overview (ex. link to product's website)
* how to get started
* overview architecture
* style guide
* how to deploy

## Development Principles

### C4

[The C4 software architecture model](https://www.structurizr.com/help/c4)

A software **system** is made up of one or more **containers**. Container is executable unit:
* web application
* mobile app
* RDS
* service
* microservice

Each container is made of one or more **components**. They can be indentified in code by names
such as components, services, modules, subsystems, layers. A component exposes a clean, well
documented public interface.

Each container is implemented by one or more **class** or function. Some classes and function
can be private to the component.

### Proverbs

* Keep in simple, stupid.
* Make it explicit.
* Test all new code.
* Comment new code.
* Make it modular, composable, testable, extensible, maintenable.
* There's no time to stop for gas, we're already late.
* If you don't understand it, you can't program it.
* If something is worth doing once, it's worth building a tool to do it.

## Automation

Automate everything. If it's not automated, it will change or be forgotten.

Run all test automatically. This can be done on every commit, once per hour, day, week,
etc. The more often you run tests the better. However, it's important that all tests are
run every so often, which will happen only if it's automated.

Automate style checking, formatting and linting.

Automate deployment. If you cannot automate all parts of deployment, write script
which does 90% and asks human to do the remaining work. Continuous delivery is the best
outcome and something worth achieving.

Automate project setup: new developer should have to run only three commands to see
the project running on their local computer:

1. Checkout code
2. Initialize environment
3. Start application

These three comments should be clearly listed in README file.

## Comments

First, code should be self-documented. The names that you use for classes, functions,
variables should tell you most of the story. Long fragments of code, statements and
expressions should be factored out into functions to give them names.

Comments should be common, but kept to minimum. Nobody has the time to read long comments,
unless they are actually needed. 80% of comments should be very short.

## Coding Style

Keep it consistant. It's best of all code in a project follows the de-facto style of
its language or framework. If there is no common style, estable it in docs. Do not try
to create style specific to the project - it won't work with opinionated developers.
Pick official style of the language or of a well known framework.

Enforce style using auto formatting tools. If it's not automatically enforced, it won't work.

## Testing

Testing principles:

* Test each public class and function.
* Test to find bugs in libraries you use.
* Test to verify your understanding.
* Test for happy and sad case.
* Test edge cases (ex. empty input).
* Keep tests verbose and linear in execution.

Testing levels:

* unit testing - one function
* component interface testing - public interface
* integration testing - few components working together
* system testing - entire system, from DB to UI

Other tests:

* performance testing
* security testing


Test for functionality. When you write test function or comment, write down:
"when ... then ..."

Mock your objects and functions. Life is so much easier with mocking. When mocking
is not available in a given language, use dependency injection pattern.
Use [Sinon.js](http://sinonjs.org/) for mocking in JavaScript.

All tests should be automated. Most tests should run periodically to ensure that they
pass. Some tests, such as performance, might be started manually, but should be otherwise
automated.

## Deployment

### Linux

* Set server to UTC timezone.
* Synchronising time: `sudo apt-get install ntp; ntpdate -s ntp.ubuntu.com;`
* Set MTU to 1500 (http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/network_mtu.html)

### Hosting

* aws.amazon.com
* godaddy.com
* rackspace.com 
* digitalocean.com  $60 / year
* namecheap.com $210 / year

### Domain

* domains.google.com

### SSL

* letsencrypt.org


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
