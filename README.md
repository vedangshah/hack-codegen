# Hack Codegen
Hack Codegen is a library for easily generating Hack code and writing it
into signed files that prevent undesired modifications.
The idea behind writing code that writes code is to raise the level of
abstraction and reduce coupling.  You can use your own way of describing
a problem and generate the corresponding code.  E.g. see examples/dorm.
In this example, we use a schema to describe the structure of the data,
and we use Hack Codegen to write the matching code.


## Examples
The DORM example shows how to use the different aspects of the code
generation in a simplified real-life example.
The included tests also exemplify the usage of the different components.


## Requirements
Hack Codegen requires:
* HHVM
* Composer

## Installing Hack Codegen
To install this package via composer, just add the package to require and start using it.

```json
{
    "require": {
        "facebook/hack-codegen": "*"
    }
}
```

## Usage
Include the autoload file generated by composer and you are ready to start using it.
For example:

```php
<?hh
require 'vendor/autoload.php';

echo codegen_file('HelloWorld.php')
  ->addClass(
    codegen_class('HelloWorld')
      ->addMethod(
        codegen_method('sayHi')
          ->setBody('echo "hello world\n";')
      )
  )->save();

```

## Configuration
You can configure some options such as the maximum line width, spacing and
headers by editing the file src/HackCodegenConfig.php

## License
Hack Codegen is BSD-licensed. We also provide an additional patent grant.