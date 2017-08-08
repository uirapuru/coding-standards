# coding-standards

For sake of teams inter-operatibility and maintaining a good coding practices in our projects,
we - developers of FutureNet group - have provided a set of rules in form of documents
and configuration files. We hope it will help to create robust, efficient and easy to understand 
solutions for business related problems in technologies that we support.

#### As your first reading this should be the site: **http://www.phptherightway.com** 

It's basically a Bible of PHP good practices.

You can install this in your project using composer:

    composer require futurenet/coding-standards
    
After successful installation testing code style and running mess detector is easy as:

    php bin/phpmd directory_to_test/ text phpmd.xml
    
    php bin/php-cs-fixer fix directory_to_test/ --dry-run --diff

For automatical fix of coding style errors run: 

    php bin/php-cs-fixer fix directory_to_test/
    
But be careful, it can be dangerous!

Reading:    

1. [Code style standards](docs/code-style.md)
2. [Architecture standards](docs/architecture.md)
3. [Testing standards](docs/testing.md)
4. [Definition of "Ready"](docs/d-o-ready.md)
5. [Definition of "Done"](docs/d-o-done.md)
6. [Running tests (to be done)](docs/running-tests.md)