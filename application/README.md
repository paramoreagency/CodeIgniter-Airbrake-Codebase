CodeIgniter Airbrake Library
============================

Wrapper library for Airbrake that works with Codeigniter and Codebase. Note: This is a fork of the library
originally created here: https://github.com/cossou/CodeIgniter-Airbrake.

# Before Updating Airbrake

If you update the Airbrake library, you *must* update the service endpoint URL found in `third_party/Airbrake/Connection.php`.

# Installation

1. Copy the files to their respective directories.
2. Set the API key in the airbrake.php config file.
3. Load the Airbrake library, either when needed or in the autoload.php config file.
4. Use the code below to send errors to Codebase:

```php
<?php

// Not needed if you auoload the library
$this->load->library('airbrake_codebase');

// Send a error message
$this->airbrake_codebase->notifyOnError('Error message'); 

// Or send an exception that may have been generated or caught.
try {
    throw new Exception('This is my exception');

} catch (Exception $exception) {
    $this->airbrake_codebase->notifyOnException($exception);
}

```

