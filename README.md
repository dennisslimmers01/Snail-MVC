# Snail - PHP Micro Framework

**_Snail_** is a small but very fast and efficient PHP framework
and contains a lot of optional features like:

  - Helper classes
  - Self developed template engine
  - Easy routing
  - Before runtime script execution
  - Backend security
  - _(Still in development)_ Database migrations
  - _(Still in development)_ Language translator
  - _(Still in development)_ Build in PHP server

# Download
Website link soon!

In the meantime you can download the zip/rar here.
https://github.com/dennisslimmers01/Snail-MVC/

# Routing

Routing in Snail is very simple. <br>

First thing you have to do is create a view!<br>
[_This can be different in your current IDE_]<br><br>
Right click on **views**, create a new php file and give it a name.<br>
The name you give your view has to be lowercase.<br>

The next thing is creating your controller.<br>
Right click on **controllers** and create a new php file.<br>
The name you give this controller has to be **camelcase** and it has to match the name of your view.<br>
So for example if the name of your view is **_'index.php'_**, your controller has to be called **_'IndexController.php'_**.<br><br>
Controller content:<br>
```php
class IndexController extends Controller {
    public function __construct() {
        parent::__construct();
        /**
         * Loads the correct model
         * based on the parameter
         *
         * access with: $this->[LOADMODEL_PARAMETER]->[FUNCTION_CALL]
         */
        $this->loadmodel('index');

        /**
         * ========================================
         * If you would like to send variables
         * to the view, it should be done in this section
         *
         * If you try to accomplish this in a
         * lower section it won't function properly
         * ========================================
         */

        $this->config_globals_array();

        /**
         * Render the correct
         * content based on the
         * parameter
         */
        $this->view->show('index');
    }
}
```


The last thing you have to do is give permission for every view you create.<br>
Navigate to app/Urls.php. Here you will see the array that contains all the routing permissions

```php
$this->urls = [
    "index",
    "debug",
];
```

Just add the name of your view to the urls array.<br>
Now if you try to navigate to for example http://localhost/snail/index <br>
you will get the correct view
