<h1 align="center">Welcome to Powerful PHP 🦾</h1>
<p>
  <a href="https://opensource.org/licenses/MIT" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
  <a href="https://twitter.com/yerenkucuker" target="_blank">
    <img alt="Twitter: yerenkucuker" src="https://img.shields.io/twitter/follow/yerenkucuker.svg?style=social" />
  </a>
</p>

> ⚡ Laravel Helpers, Collections and Js like object oriented chaining for Native PHP 

## Install

```sh
composer require erenkucukersoftware/powerful-php
```
## 🚀 Usage

### Object Oriented Chaining

#### Example 1 :
##### Functional Approach 

```php

$snakeCase = strtolower(
    preg_replace('/(.)(?=[A-Z])/u', '$1_', 
        preg_replace('/\s+/u', '', 
            ucwords('HelloWorld')
        )
    )
);
             
var_dump($snakeCase); // "hello_world"
```

##### Object Oriented Approach 

```php
//powerfulphp

$snakeCase = 
    pipe('Hello World')
    ->ucwords(_)
    ->preg_replace('/\s+/u', '', _)
    ->preg_replace('/(.)(?=[A-Z])/u', '$1_', _)
    ->strtolower(_)
    ->var_dump;
//
// string(11) "hello_world"
//
```

#### Example 2 :

##### Passing Value Between Pipes

To pass a value as an argument to a function, use the underscore (_) character :
```php
pipe('hello')
    ->str_replace('o', '', _)
    ->var_dump; // "hell"
```

#### Example 3 :

##### One Parameter Usage

You can omit parentheses if only one argument is used:

```php
pipe('some')
    ->is_array
    ->dd; // bool(false) 
```

#### Example 4 :

##### Values


```php
$context = pipe('hello')->strtoupper;

var_dump($context);
// object(Fun\Pipe\Pipe)#8 (1) { ... } 

var_dump($context());
// string(5) "HELLO"
```

#### Example 5 :

##### Namespaces

Calling single function from namespace
```php
pipe()
    ->use('Some\\Namespace')->foo // Call "\Some\Namespace\foo()"
    ->foo // Call "\foo()"
;

```

Calling multiple function from namespace
```php
pipe()
    ->use('Some\\Namespace', fn($pipe) => 
        $pipe
            ->a // Call "\Some\Namespace\a()"
            ->b // Call "\Some\Namespace\b()"
    )
    ->a // Call "a()"
;

```



## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request




## Author

👤 **Eren Küçüker**

* Website: www.erenkucuker.com
* Twitter: [@yerenkucuker](https://twitter.com/yerenkucuker)
* Github: [@erenkucukersoftware](https://github.com/erenkucukersoftware)
* LinkedIn: [@yunus-eren-küçüker-609716168](https://linkedin.com/in/yunus-eren-küçüker-609716168)

## Show your support

Give a ⭐️ if this project helped you!

<a href="https://www.patreon.com/erenkucuker">
  <img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="160">
</a>

## 📝 License

Copyright © 2021 [Eren Küçüker](https://github.com/erenkucukersoftware).<br />
This project is [MIT](https://opensource.org/licenses/MIT) licensed.
