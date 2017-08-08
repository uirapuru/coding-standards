# testing standards

We use tools:

* [phpunit](http://phpunit.de) (with [prophecy](phpspec/prophecy))
* [doctrine/data-fixtures](https://github.com/doctrine/data-fixtures) and/or [nelmio/alice](https://github.com/nelmio/alice)
* [faker/faker](https://github.com/fzaninotto/Faker)

## Directory structure

We keep our test files in directories that mirrors the structure of project, i.e. for a class

```./src/FutureNet/App/Service/MainProvider.php```

we create a test in directory:

```./tests/Unit/FutureNet/App/Service/MainProviderTest.php```

Namespace of this class should be:

```Tests\Unit\FutureNet\App\Service\MainProviderTest```

If we need to create a abstract test class, then we need to add a "Case" suffix to it's name so
it's not going to be run by phpunit:

```./tests/Functional/AbstractFunctionalTestCase.php```

Files used for testing and fixtures should be also organized:

```
./tests/Functional/Resources/music_files/audio.mp3
./tests/Functional/Resources/images/picture.jpg
./tests/Functional/Resources/fixtures/customers.yml
./tests/Functional/Resources/fixtures/projects.yml
```

## Test naming

We mark test method with annotation and we keep name as descriptive as possible. We write down an action,
current state and expectation in snake case format:

```php
    <?php
    
    use PHPUnit\Framework\TestCase;
    
    class Test extends TestCase {
        
    
        /**
          * @test
          */
        public function getting_of_an_inexisting_playlist_throws_404(){}
        
}
```

## Testing exceptions

Keep assertions for exception in the code - don't use annotations for that, so you can control it through the code and use for example with Data Provider:


```php
    <?php
    
    use PHPUnit\Framework\TestCase;
    
    class Test extends TestCase {
        
    
        /**
          * @test
          * @dataProvider providerForValidator
          */
        public function validation_will_throw_an_exception_for_input($input, $class, $message){
            $this->expectException($class);
            $this->expectExceptionMessage($message);
            
            $validator->validate($input);
        }
        
        public function providerForValidator() : array {
            return [
                "invalid email" => [
                    "input" => "not_an_email",
                    "class" => InvalidEmail::class,
                    "message" => "not_an_email is an invalid email"    
                ],
                "invalid age" => [
                    "input" => -10,
                    "class" => InvalidAge::class,
                    "message" => "You can't be -10 years old!"    
                ],    
            ];
        }
        
}
```

## Test fixtures and database

Use easy to maintain expressive code or yaml files for holding fixtures (like EloquentFactory or Nelmio/AliceBundle or Doctrine/Data-Fixtures).
In special cases you can clean and populate your db directly in the test class.

Database should be cleaned and resetted after every test (use setUp() and tearDown() methods for that).

# Other important stuff

Keep your test standalone and separated. Tests must can be runned in any order without impacting each other. 

Don't test code of vendor libraries. They're tested already by author (if not - don't use them at all).
But remember that you have to test how your code works with vendor library.

Don't test remote services. Mock them or create your stubs, simulating different responses. You can still have this kind of test though,
but keep them in separated suite (for testing payments for example). Remember that this kind of test can easily fail if there's no
internet connection etc.

Remember about optimization. All the tests should be passed under 2 minutes. Remember about possibility of switching to InMemory 
storage or sqlite database. You can also divide tests into suits (slow and fast tests etc.)

**TEST IS A DOCUMENTATION OF FEATURE**. Write it in a way that is readible and easy to change and maintain. It should be easy
to understand by someone new to project.

Always test a successful scenario, but for every "right" way there's a 10 or more cases of erroneous scenarios that has to be tested.
As in the joke: `A code tester walks into a bar. Orders a beer. Orders ten beers. Orders 2.15 billion beers. Orders -1 beers. Orders a nothing. Orders a cat. Tries to leave without paying.`  
