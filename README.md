Xbox API Wrapper
===================

Version: 1.1

A simple PHP wrapper for the [XboxLeaders.com Xbox API](https://www.xboxleaders.com/)

[Blog](https://www.xboxleaders.com/blog/) | [Forums](https://www.xboxleaders.com/forums/)


License
=======

The XboxLeaders API Wrapper is licensed under [MIT License](http://opensource.org/licenses/mit-license.php)


Requirements
============

* PHP 5.2+
* [cURL](http://php.net/curl) PHP Extension
* [JSON](http://php.net/json) PHP Extension
* [SimpleXML](http://php.net/simplexml) PHP Extension
* [PHP Serialize/Unserialize](http://php.net/unserialize)


Installation
============

Simply include the `/lib/wrapper.php` file into whatever script you are going to be using the API for, and instantiate the `XboxApi` class.


        <?php
        require 'wrapper.php';
        
        $api = new XboxApi();
        $api->format = 'json';  // format to request results
        $api->timeout = 6;      // set timeout for request
        $api->version = '2.0';  // version of api to use
        $api->region = 'en-US'; // region to return results from
        
        $games = $api->fetch_games('Major Nelson');


Methods
=======

`$this->fetch_profile($gamertag);` Returns all data associated with the requested gamertag such as Gamerscore, Reputation, and Biography.

`$this->fetch_games($gamertag);` Returns all played games and associated data related to those games, except individual achievements.

`$this->fetch_achievements($gamertag, $gameid);` Returns all achievements and their associated data for the requested gamertag and game.

`$this->fetch_friends($gamertag);` Returns a list of all of the requested gamertags' friends, and their associated data.

`$this->fetch_search($query);` Returns an array of search data from the Xbox Marketplace for the given query.
