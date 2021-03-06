Drupal App Console | The symfony console in Drupal
==============

Drupal 8 has changed a lot the way we develop websites, the idea of this project is to provide similar functionality as the Symfony console, providing a scaffolding tool to automate the creation of modules using the terminal to automatically generate the directory structure for controllers, forms, services and required files.

The DrupalAppConsole not is a competition of Drush it’s your new best friend.

### Steps for install:

```bash
$ cd path/to/drupal8.dev
$ curl -sS https://getcomposer.org/installer | php
$ COMPOSER_BIN_DIR=bin php composer.phar require hechoendrupal/drupal-app-console:dev-master
$ ./bin/console --help
```

### Usage

#### Generate module structure
```bash
$ ./bin/console generate:module
                                          
  Welcome to the Drupal module generator  
                                          
Module name: module_name
Description [My Awesome Module]: My awesome module 
Package [Other]: My Package
Do you want to generate a routing file [yes]? yes
Do you want to generate the whole directory structure [no]? yes
Do you confirm generation [yes]? 

$ tree modules/module_name/
modules/module_name/
├── config
├── lib
│   └── Drupal
│       └── module_name
│           ├── Controller
│           ├── Form
│           ├── Plugin
│           │   └── Block
│           └── Tests
├── templates
├── tests
├── module_name.info.yml
├── module_name.module
└── module_name.routing.yml

11 directories, 3 files
```

#### Generate controller structure
```bash
$ ./bin/console generate:controller

  Welcome to the Drupal controller generator  
                                              
Enter your module: : module_name
Enter the controller name [DefaultControler]: FrontController
Enter your service: : twig
Enter your service: : database
Enter your service: : config.factory
Enter your service: : config.context
Enter your service: : 
Update routing file? [yes]? 

$ cat modules/module_name/lib/Drupal/module_name/Controller/FrontController.php
```

#### Generate form structure
```bash

  Welcome to the Drupal form generator  
                                        
Enter your module : module_name
Enter the form name [DefaultForm]: 
Do you like asdd service? [yes]? 
 Enter your service: twig
 Enter your service: config.factory
 Enter your service: 
Do you like generate a form structure? [yes]? 
 Input label: User
  Input machine name [user]: 
  Type: text
 Input label: Password
  Input machine name [password]: 
  Type: password
 Input label: Send
  Input machine name [send]: 
  Type: submit
 Input label: 
 Do you like generate config file? [yes]? 
Update routing file? [yes]? 

```

#### Next Step
* Enable module
* Open Browser and load `http://drupal8.dev/module_name/hello/Drupal`

#### Video
[How to install & use youtube video no audio](http://www.youtube.com/watch?v=NkHT2KctR-Y)
