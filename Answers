### Issue 1

The customer disabled WP Rocket’s automatic cache clearing system. They want you to provide them with a way to clear the following cache files at a specific time they select, e.g. when the site has the least traffic:

- HTML
- Combined/minified CSS/JavaScript files

Using WP Rocket’s existing functions:

1. Explain how they should implement the requirement to clear the cache at a specific time.
2. Provide any piece of code necessary to perform the cache clearing task.

Hi mate,

I would recommend sending the following to the client:

Hi there,

Thanks for contacting WP Rocket support.

The following steps will guide you to install a cron job to clear the HTML, Combined/minified, and CSS/JavaScript files every day at specific time:

1- Make a full website backup before proceeding with the following steps.

2- First, you need to disable WP Cron, so it's not executed every time someone loads one of your pages. 
To disable it, open the wp-config.php file in your main WordPress folder and add the following line before the "/* That's all, stop editing! Happy blogging. */" line:

`define('DISABLE_WP_CRON', true);`

3- Add a Cron job entry through your web hosting control pane. Please remember to replace the yourdomain.com with the client actual domain:
wget -q -O - http://yourdomain.com/rocket-clean-domain.php

You need to pick the time to run the cron job from your CPanel as explained in this video: https://recordit.co/cl2YCoMCzu
	

3- Create a PHP file and name it: rocket-clean-domain.php
Add the following code to rocket-clean-domain.php

```<?php 
// Load WordPress.
require( 'wp-load.php' );

// Clear cache.
if ( function_exists( 'rocket_clean_domain' ) ) {
	rocket_clean_domain();
 }
// Preload cache.
if ( function_exists( 'run_rocket_sitemap_preload' ) ) {
	run_rocket_sitemap_preload();
}```

4- Upload this file to your WordPress installation's root ( where wp-config.php and wp-load.php are located).
Note: If you place it in a different location, you need to edit the path in require( 'wp-load.php' ); above to match its location.

This page will guide you on how to use a cron job and clear the cache manually:
https://docs.wp-rocket.me/article/494-how-to-clear-cache-via-cron-job#clear-preload-specific-page

### Issue 2

Your teammate sent your instructions and code to the customer.

They implemented them but the cache isn’t cleared.

Provide the steps that you’d follow to troubleshoot this, based on the solution you provided in **Issue 1**.

Assume that:

- you have tested your code on your environment and it works fine and
- the customer has provided you access to their site/server.

You need to check if the wp-cron is disabled in the client wp-config.php file and make sure it has been replaced with a server cron.

If you have done these things but are seeing the notice anyway, please redirect the client to contact his website host to check if and why cron is not working as expected.

https://docs.wp-rocket.me/article/1422-the-following-scheduled-event-failed-to-run
