Formatter Bundle
================

Laravel Bundle ported from the FuelPHP Format class, that helps you easily convert between various formats such as XML, JSON, CSV, etc...

Installation
------------
Using artisan to install the bundle

```
php artisan bundle:install formatter
```

Or you can clone the bundle straight from github. Run the following command inside your bundles folder:

```
git clone git@github.com:rodrigore/laravel-formatter.git formatter
```

Add the Following to your application/bundles.php file:

```
'formatter' => array('auto' => true) // you can leave out the auto => true
```

That's it, Formatter should now be installed and ready to go!

Usage
-----
The best way to learn how to use Formatter is to look through the code, where you can familiarize yourself with all of the available methods.

###Calling Formatter

Formatter::make($data_to_convert, 'type of data')->to_the_format_you_want();

### Available Formats to Convert From
- Json
- Serialized Array
- XML
- CSV

### Available Formates to Convert To
- Json
- Serializaed Array
- XML
- CSV
- PHP Array
- PHP Export
- YAML

```
$json_string = '{"foo":"bar","baz":"qux"}';
print_r(Formatter::make($json_string, 'json')->to_array());

// Returns
Array
(
    [foo] => bar
    [baz] => qux
)
```

### Handling errors from csv

To check if an error was ocurred when you use the method from_csv, you can use the array call errors.

```
// Post use of Formatter::make($file, 'csv')
if ( ! empty(Formatter::$errors) ) {
    // Show the errors
    print_r(Formatter::$errors);
}
```
The exception were replaced and added to the array of errors. Also, if the CSV file contains a row with more o less data than the headings this errors are store in this array.

### Spanish Folder

The es Folder was added, with the two messages from the exception and the news errors.

### ToDo

* Check if the replaced of Exception to messages are ok.
* Add more validation to the csv file.
* Add more error messages to the other methods.