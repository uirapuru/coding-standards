# general standards

1. [Definition of "Ready"](docs/d-o-ready.md)
2. [Definition of "Done"](docs/d-o-done.md)

# coding-standards for backend developers

For sake of teams inter-operatibility and maintaining a good coding practices in our projects,
we - developers of FutureNet group - have provided a set of rules in form of documents
and configuration files. We hope it will help to create robust, efficient and easy to understand 
solutions for business related problems in technologies that we support.

# As your first reading

this should be the site: **http://www.phptherightway.com**
It's basically a Bible of PHP good practices.

also nice to know and understand: **https://github.com/jupeter/clean-code-php**
and a league of outstanding packages: **https://github.com/ziadoz/awesome-php/blob/master/README.md**

# Installation

You can install this in your project using composer:

    composer require futurenet/coding-standards
    
After successful installation testing code style and running mess detector is easy as:

    php bin/phpmd directory_to_test/ text vendor/futurenet/coding-standards/phpmd.xml
    
    php bin/php-cs-fixer fix directory_to_test/ --dry-run --diff --config=vendor/futurenet/coding-standards/.php_cs.dist

For automatical fix of coding style errors run: 

    php bin/php-cs-fixer fix directory_to_fix/ --config=vendor/futurenet/coding-standards/.php_cs.dist
    
But be careful, it can be dangerous!

Reading:    

1. [Code style standards](docs/code-style.md)
2. [Architecture standards](docs/architecture.md)
3. [Testing standards](docs/testing.md)
4. [Running tests (to be done)](docs/running-tests.md)

# frontend coding standards

This set of good front-end coding practices has been introduced to optimize the time it takes to implement the external content provided to FutureNet developers, and to facilitate mutual communication between them and external teams.

Developed by us (FutureNet developers) good coding practices have been based on our own knowledge and experience, and also based on the external standards used by front-end developers everyday around the world.

The collection was divided into three parts, in which the standards described were enriched with practical examples.

Reading:
1. [CSS standards](docs/css.md)
2. [HTML standards](docs/html.md)
3. [JS standards](docs/js.md)