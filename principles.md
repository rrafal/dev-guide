# Web Development Principles

These are best rules and practices in web software development. I did not invent
any of the things I'm writing about. Either I stole them from people who are smarter and better,
or I discovered them the hard way - doing the same thing over and over and learning along the way.

These rules are not a law which must be followed. Instead, they are best practicies which
are worth to follow when it makes sense. They are practices relevent to what I work on,
to the tools and technologies I use, to the problems I solve. They might not work well,
or might not be applicable for other engineers. Also, they might become irrelevant for me
in a few year. Notherless, I think it's worth the time to write them down. First, it will
remind me what rules I want to follow but do not necesserly do. Second,
it might help others to understand who I am as a software engineer. Third, somebody might come
across this document and find it useful.

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

## Proverbs

* Keep in simple, stupid.
* Make it explicit.
* Test first, test all, test often.
* Code comments out.
* Composition over inheritance.
* Make it modular, composable, testable, extensible, maintenable.
* There's no time to stop for gas, we're already late.
* If you don't understand it, you can't program it.
* If something is worth doing once, it's worth building a tool to do it.

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

## C4 Architecture 

[The C4 software architecture model](https://www.structurizr.com/help/c4) describes software
in four layers, from most generic to most detail. They are system context, containers,
components and classes.

A **system context** describes all involved parties and tools. It includes users, admins,
and 3-rd party APIs.

The system is made of one or more **containers**. Container is an executable unit:
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
