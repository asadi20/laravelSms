laravelSms
==========

package for send sms with laravel (published for [parssms24.ir](http://parssms24.ir)) this package only work for iranian mobile operator

installation
------------
For install this package Edit your project's ```composer.json``` file to require livana/sms

```php
"require": {
    "livana/sms": "dev-master"
},
```
Now, update Composer:
```
composer update
```
Once composer is finished, you need to add the service provider. Open ```app/config/app.php```, and add a new item to the providers array.
```
'Livana\Sms\SmsServiceProvider',
```
Next, add a Facade for more convenient usage. In ```app/config/app.php``` add the following line to the aliases array:
```
'Sms' => 'Livana\Sms\Facades\Sms',
```
Publish config files:
```
php artisan config:publish livana/sms
```
for change username, password and other configuration change ```app/config/packages/livana/sms/config.php```

Usage
-----
for use this package, please register on [parssms24.ir](http://parssms24.ir)

### Send Message
```php
Sms::send('9123456789', 'text message'); // send message for a person

Sms::send(['9123456789', '91234567890'], 'text mesage'); // send message for persons
```
### Get Credit
```php
Sms::getCredit();
```
