Display which environment you are on **at all times** in the CP so you don't accidentally do something bad on the production environment. In your config.php, set an ENV variable like so:

<pre>if(!defined('ENV')) {
	switch ($_SERVER['SERVER_NAME']) {
		case 'site.com':
			define('ENV', 'prod');
		break;
		
		case 'stage.site.com':
			define('ENV', 'staging');
		break;
	
		default:
			define('ENV', 'local');
		break;
	}
}</pre>

The value of ENV will be injected into the header of the CP and fixed to the screen as you scroll.

*Note: only shown to Super Admins.*