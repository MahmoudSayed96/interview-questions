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
 > The `final` keyword is used to prevent a class from being inherited and to prevent inherited method from being overridden.
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
  > the Laravel JWT Auth package, that the token is still being stored on the *server (using Laravel's cache system)* by default
7. Reflaction Class in PHP.
8. Eger loading VS. Lazy loading in laravel.
9. Laravel Request LifeCycle.
  ![Request Cycle](laravel-request-lifecycle.jfif)
10. Laravel Service Provider
   [Laravel Service Provider](https://www.youtube.com/watch?v=VYPfncvYW-Y&t=208s)
   [Arabic](https://5dmat-web.com/ar/playlist/31/%D8%AF%D8%B1%D9%88%D8%B3_%D9%85%D8%AA%D9%82%D8%AF%D9%85%D8%A9_%D9%81%D9%8A_laravel)
11. Laravel Service Container
   > Manage classes dependancies
    [Arabic](https://www.youtube.com/watch?v=Tnko0sRKQUU)
12. What is Abstraction Concepts?
  > Abstraction is the concept of object-oriented programming that "shows" only essential attributes and "hides" unnecessary information. 
  > The main purpose of abstraction is hiding the unnecessary details from the users.
13. What is Closure Function and pass by value or refrence?.
  ```php
    $products = Product::with(['category' => function ($q) use ($request) {
              // This is closure function.
              // pass by value to pass by ref using '&$request'
              return $q->where('status', 1);
     }]);
  ```
 14. What is diff `truncate` , `delete` and `drop` in database?.
  **TRUNCATE**.
  > TRUNCATE Command is a Data Definition Language operation. It is used to remove all the records from a table. 
  > It deletes all the records from an existing table but not the table itself. The structure or schema of the table is preserved.
  >
  > Truncate command marks the table for deallocation. This operation removes all the data from a table bypassing a number of constraints 
  > enforced on the table. *MySQL does not allow the users to truncate the table which is referenced as FOREIGN KEY in another table*.

 **DELETE**.
  > The DELETE statement in SQL is a Data Manipulation Language(DML) Command. It is used to delete existing records from an existing table.
  >  We can delete a single record or multiple records depending on the condition specified in the query.
  >
  > The conditions are specified in the WHERE clause of the DELETE statement. If we omit the WHERE clause then all of the records 
  > will be deleted and the table will be empty.
  > The DELETE statement scans every row before deleting it. Thus it is slower as compared to TRUNCATE command. If we want to delete all the records of a table,
  > it is preferable to use TRUNCATE in place of DELETE as the former is faster than the latter.

**DROP**.
 > DROP statement is a Data Definition Language(DDL) Command which is used to delete existing database objects. 
 > It can be used to delete databases, tables, views, triggers, etc.
 > A DROP statement in SQL removes a component from a relational database management system (RDBMS).

15. What is `csrf` in laravel ?.
  > This CSRF token is generated automatically for each user. This token is nothing but a random string that 
  > is managed by the Laravel application to verify the user requests.
  >
  > How to Use: This CSRF token protection can be applied to any HTML form in Laravel application by 
  > specifying a hidden form field of CSRF token. The requests are validated automatically by the CSRF VerifyCsrfToken middleware.
  > There are three different ways in which you can do this.
  > @csrf
  > csrf_field(): This function generate hidden html element.
  > csrf_token(): This function just gives a random string.

16. What the poroblem `CROS` and why happend?
17. What is OOP in PHP?
 *OOP stands for Object-Oriented Programming*.
 > Procedural programming is about writing procedures or functions that perform operations on the data, while object-oriented programming 
 > is about creating objects that contain both data and functions.
 > 
 > Object-oriented programming has several advantages over procedural programming:
 > OOP is faster and easier to execute
 > OOP provides a clear structure for the programs
 > OOP helps to keep the PHP code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
 > OOP makes it possible to create full reusable applications with less code and shorter development time.
 
18. **SOLID**
 - **S**ingle Respons
 - [**O**pen/Close](/open-closed-principle-php-arabic.pdf)
 - [**L**iskov](liskov-substitution-principle-php-arabic.pdf)
 - [**I**nterface Segregation](Interface-segregation-principle-arabic.pdf)
 - [**D**ependency Inversion](dependency-inversion-principle-php-arabic.pdf)
