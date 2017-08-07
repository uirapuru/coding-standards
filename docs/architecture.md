# architecture

1. Untestable or untested code **is not working** (despite the fact that you manually clicked it many times and it was working yesterday).
   It builds an technological debt - someone will have to pay it at the end. Keep this in mind, don't use shortcuts and keep you techdebt
   as small as possible.

2. [Single Responsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle) - there are so many things to do in the code,
   be sure none of it is doing someone's other business. I.e.: controller is only parsing a Request into Response. Move away
   all other logic into separate class. Thanks to this you can easily test both. Methods are named after actions they are doing,
   no reason for `$reposityory->insert($user)` to send an email. 

3. Rules like
   * [S.O.L.I.D.](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))
   * [K.I.S.S.](https://en.wikipedia.org/wiki/KISS_principle)
   * [D.R.Y.](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
   
   are non-disputable. You just **HAVE to** know them, but more important - use them and use them in a **good way**.
      
4. [Command-Query Separation](https://en.wikipedia.org/wiki/Command%E2%80%93query_separation) - it's easy as this:
   
   * you can change a state of system, but you don't read anything
   * you can read something, but you don't change a state of system
   
   Sometimes it's get tricky to do something without two or more calls,
   but you can for example create an entity with already generated ID that you know
   and only then save it to database. 
   
5. Avoid of breaking rule of [encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)).
   There is no point to create such a code because you get full access to the protected/private field:
   
   ```php
   <?php
  
   class Object {
    
    private $field;
 
    public function getField() { return $this->field; }
    
    public function setField($value) { $this->field = $value; }

   }
   ```
   
   Instead think how to create a bullet-proof object that it's almost inmutable
   - so you gain full control on his state. Consider this:
   
   
  ```php
  <?php
  
  class User {
    private $firstname;
    
    private $lastname;
    
    private $email;
    
    private $active = false;
    
    private $roles = [];
    
    private function __construct($firstname, $lastname, $email, $active, $roles) {
        $this->firstname = $firstname;
        $this->lastname = $lastname;
        $this->email = $email;
        $this->active = $active;
        $this->roles = $roles;
    }
    
    public static function create($firstname, $lastname, $email) : self {
        return new self($firstname, $lastname, $email, true, ["ROLE_USER"]);
    }
    
    public function updateData(DTO\UpdateUserName $dto) {
        if($dto->firstname !== null) {
            $this->firstname = $dto->firstname;
        }
        
        if($dto->lastname !== null) {
            $this->lastname = $dto->lastname;
        }
    }
    
    public function updateEmail(DTO\UpdateEmail $dto) {
        if($dto->email !== null && $dto->isValidEmail()) {
            $this->email = $dto->email;
        } else {
            throw new Exception("Email invalid");
        }
    }
  }
  
  $user = User::create("John", "Rambo", "rambo@gmail.com");
  
  $user->updateEmail(new DTO\UpdateEmail("rambo@yahoo.com"));
  
  ```
  
  As you can see - no setters (!!!), and you can change only through the specific methods,
  using dto object with logic for validation. Important stuff is immutable - less errors.
  
6. Instead of inheriting classes use composition and architectural/design
   patterns to augment your code. Remember about Interface segregation. Use traits.
   There's a special place in hell for people doing:
   
   ```php
   <?php

   abstract class AbstractEntity;
   
   abstract class AbstractUser extends AbstractEntity;
   
   abstract class AbstractAdmin extends AbstractUser;

   class RegularAdmin extends AbstractAdmin;
   
   ```
   
   this is better:
   
   ```php
      <?php
   
      class RegularAdmin implements UserInterface, EntityInterface
      {
      
           use SpecialSuperPowers;
           
           /// ...
      };
      
    ```
   
   Avoid of using inheritance. 1-degree level inheritance can be ok. If it's 2 or more
   - you're probably doing something wrong.

7. Start measuring your code.
   * start using [XDebug](http://xdebug.org). It's a must.
   * Use logging (to the log files, to db or syslog - does not matter)
   * Use convenient error reporting (i.e. [Sentry](http://sentry.io), Munin, NewRelic )
   * Use a good library for dumping data

8. Start measuring your tests and optimize them. Tests can be divided into smaller units and suites that
   should last not longer than 2 minutes. Developer should be able to run them quickly on his local machine.
   
   
  