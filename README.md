# BulkSMS.com API Package Wrapper

[![Latest Version on Packagist](https://img.shields.io/packagist/v/epmnzava/bulksms.svg?style=flat-square)](https://packagist.org/packages/epmnzava/bulksms)
[![Quality Score](https://img.shields.io/scrutinizer/g/dbrax/bulksms.svg?style=flat-square)](https://scrutinizer-ci.com/g/epmnzava/bulksms)
[![Total Downloads](https://img.shields.io/packagist/dt/epmnzava/bulksms.svg?style=flat-square)](https://packagist.org/packages/epmnzava/bulksms)

This package provides a convenient API wrapper for BulkSMS.com, designed for seamless integration into PHP and Laravel projects.

## Installation

**Requirements:**

- Laravel: ^7.2 to ^9.0
- PHP: ^7.1, ^7.2, ^7.3, ^7.4, or ^8.0

Install the package using Composer:

```bash
composer require epmnzava/bulksms
```

## Configuration

### Laravel (5.4 and below)

1. Add the service provider to the `providers` array in `config/app.php`:

    ```php
    Epmnzava\Bulksms\BulksmsServiceProvider::class,
    ```

2. Add the facade to the `aliases` array in `config/app.php`:

    ```php
    'BulkSms' => Epmnzava\Bulksms\BulksmsFacade::class,
    ```

### Laravel (5.4 and above)

Publish the configuration file using Artisan:

```bash
php artisan vendor:publish --provider="Epmnzava\Bulksms\BulksmsServiceProvider"
```

## Environment Variables

Configure the following environment variables in your `.env` file:

```bash
BULKSMS_SENDERID="YourSenderID"
BULKSMS_SECRET="YourSecretToken"
BULKSMS_ID="YourTokenID"
```

Replace `YourSenderID`, `YourSecretToken`, and `YourTokenID` with your actual BulkSMS.com credentials.

## Usage

### Sending a Simple Text Message

```php
<?php

use Epmnzava\Bulksms\Bulksms;

class SendSmsController
{
    public function sendSms()
    {
        $sms = new Bulksms;
        $response = $sms->sendMessage("+255679079774", "Just testing, please receive blessings.");

        // Example response:
        /*
            {
                server_response: "[ { "id" : "953262833859043328", "type" : "SENT", "from" : "PamojaWeCan", "to" : "255679079774", "body" : "hellow man", "encoding" : "TEXT", "protocolId" : 0, "messageClass" : 0, "submission" : { "id" : "2-00000000001865236111", "date" : "2021-03-15T12:06:10Z" }, "status" : { "id" : "ACCEPTED.null", "type" : "ACCEPTED", "subtype" : null }, "relatedSentMessageId" : null, "userSuppliedId" : null, "numberOfParts" : null, "creditCost" : null } ]",
                http_status: 201,
                error: ""
            }
        */

        // You can then handle the $response as needed.
    }
}
```

## Testing

Run tests using Composer:

```bash
composer test
```

## Changelog

See [CHANGELOG.md](https://www.google.com/url?sa=E&source=gmail&q=CHANGELOG.md) for a history of changes.

## Contributing

Please refer to [CONTRIBUTING.md](https://www.google.com/url?sa=E&source=gmail&q=CONTRIBUTING.md) for contribution guidelines.

## Security

For security vulnerabilities, please email [epmzava@gmail.com](mailto:epmzava@gmail.com) instead of using the issue tracker.

## Credits

- [Emmanuel Paul Mnzava](https://github.com/dbrax)
- [All Contributors](../../contributors)

## License

This package is licensed under the MIT License. See [LICENSE.md](https://www.google.com/url?sa=E&source=gmail&q=LICENSE.md) for details.
