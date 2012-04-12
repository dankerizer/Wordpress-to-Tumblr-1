#Wordpress to Tumblr 

##About 

PHP script that help to export Wordpress posts to Tumblr.

It can serve as a basis because it contains the resolution of several export issues :

 
##Features

- Support secondary Tumblr blog for destination ( group )

- Import Tags

- Import posts types according to categories

- Use custom fields to import

- Make a list of source/destination posts URL to easily create redirections rules ( eg. redirect permanent 301 Apache )

- Deals with [sourcode] and [caption] Wordpress shortcodes ( using the [backpress](http://backpress.org/)  shortcodes lib )

- Sourcecodes can be highlighted with [google-code-prettify](http://google-code-prettify.googlecode.com/)

- Fill the Tumblr post Slug with the Wordpress post name



 
##Configuration

Copy, rename and edit the sample configuration file __config.php.sample__ to __config.php__

##Prerequisites
Wordpress posts are beforehand arranged in a specific category that represent the posts types ( $tumblogWPCategory in config.php ).

##Photos and images
Photos are _automagically_ uploaded to Tumblr when using the _photo_ post type.
However, images of the post body are not uploaded. You have to maintain them in a CDN for instance.
In the config file, you can relocate images paths using the $relocateBodyImages array.

    $relocateBodyImages = array( 
    "http://myblog.com/wp-content/uploads/" 
    => "media.myblog.com/tumblelog/"
    );

##Redirection

In the config file, indicate a file name for $logFile.

The log file is in the CSV format :

     source-URL ; destination-URL
 
So you can easily create rules for your web server. 

    Redirect permanent source-URL destination-URL 
    
##Misc

The script `delete-tumblr-post.php` is a utility to delete all post of the tumblr blog. 

These scripts use the [Tumblr API v1](http://www.tumblr.com/docs/en/api)


###Disclaimer

This script is based on the [Wordpress-to-Tumblr](https://github.com/thetylerhayes/Wordpress-to-Tumblr.git) script, but it's not a Fork in view of all changes and additions that are made.
 
