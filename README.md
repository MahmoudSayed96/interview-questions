# interview-questions
List of questions that i asked in interviews

1 - What is Dependancy Injection?
> Object dependant on another Object in example `Post` class depend on `User` class
```php
class User {
  public $username;
  public $userAge;
  
  public function __constructor() {
  
  }
}

class Post {
  public $postTitle;
  public $postBody;
  public $user;
  public function __constructor() {
    // ...
  }
  
  public function setUser(User $user) {
    $this->user = $user;
  }
}
```
Why don't use class in constructor?
> Becouse with each `Post` object created we need to pass user object to constructor.

2 - Why using `localStorage` in javascript to store data and not using `Cookies` ?
> Becouse cookies send to server with each request but localStorage don't do this

3 - What is diff between `Cookies` and `Sessions` and worked in server or client?
> The main difference between a session and a cookie is that `session` data is stored on the server, 
> whereas `cookies` store data in the visitor’s browser.

> Sessions are more secure than cookies as it is stored in server. Cookie can be turned off from browser.

> Data stored in `cookie` can be stored for months or years, depending on the life span of the cookie. 
> But the data in the `session` is lost when the web browser is closed.

4 - What is `final class` and why use it ?

5 - What is diff between `abstract` ,`final` and `interface` class ?
- Abstract class vs Interface.
  > Interface using for make blueprint structure.
  > 
  > Abstract cannot be instantiated.
1. **Methods Type**
  > `interface`: Contains only declered functions and public access.
  > 
  > `abstract`: Contains declered and implemetaion functions.
  ```php
  interface A
{
    public function foo();
}

abstract class B {
    public function foo(): string
    {
        return 'foo';
    }

    public abstract function buz();
}
  ```
2. **Inheritance**
  > `interface`: Multiple inheritance.
  > 
  > `abstract`: Single inheritance.
  ```php
  interface A {}
  interface B {}
  interface C {}
  interface D extends A, B, C {}

  abstract class A{}
  abstract class B extends A{}
  ```
 3. Properties
   > `interface`: No properties.
   > 
   > `abstract`: Has properties.
4. Access Modiferies
   > `interface`: Public only.
   > 
   > `abstract`: Any.
**Final Class**.
> Final Class: A class which is declared with the `Final` keyword is known as the final class. 
> The final keyword is used to finalize the implementations of the classes, the methods and the variables used in this class.
> 
> *The main purpose of using a final class is to prevent the class from being inherited*.

6. How laravel/JWT sotre use token in server?

7. Reflaction Class in PHP
8. Eger loading VS. Lazy loading in laravel
