# code style

We all need an easy to read source code, because it is itself **the best** type of documentation.
That's why we came up with following rules:

1. We stick to [Symfony2](https://symfony.com/doc/current/contributing/code/standards.html) coding standard
   and [PSR-0](http://www.php-fig.org/psr/psr-0/), [PSR-1](http://www.php-fig.org/psr/psr-1/), [PSR-2](http://www.php-fig.org/psr/psr-2/)
   and [PSR-4](http://www.php-fig.org/psr/psr-4/) rules.

2. Don't use [Hungarian Notation](https://en.wikipedia.org/wiki/Hungarian_notation) - in time of type hinting and PHP7 it has no point.

3. Don't use words like *Provider or *Manager etc. in class names because it's biasing the real point of a class,
   can break the [SRP rule](https://en.wikipedia.org/wiki/Single_responsibility_principle) and can encourage developers to
   put more and more code into this class which will became a "trashcan" for different code. Use explicit name instead,
   that will clearly describe responsibility of the object.

4. Always name your objects, methods and variables after the things that they really are. This is bad:

   ```php
   foreach($tmp as $i => $j);
   ```

   And this is good:

   ```php
   foreach($usersWithBasket as $userEmail => $productInTheBasket);
   ```
   
   Variables like $a, $i, $j, $k, $tmp, $temp are a **nightmare** for a reader! Longer and descriptive variable
   name is better than a short one.
