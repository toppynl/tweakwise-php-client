# Tweakwise PHP Client

A PHP client library for the Tweakwise API, providing access to search, navigation, recommendations, and other e-commerce services.

## Installation

Install the package using Composer:

```bash
composer require toppy/tweakwise-client
```

## Requirements

- PHP 8.1 or higher
- cURL extension
- JSON extension
- Mbstring extension

## Quick Usage

```php
<?php
require_once 'vendor/autoload.php';

use Toppy\TweakwiseClient\Configuration;
use Toppy\TweakwiseClient\Api\NavigationApi;

// Configure the client with your Tweakwise instance key
$config = Configuration::getDefaultConfiguration();
$config->setApiKey('tn-key', 'your-tweakwise-instance-key');
$config->setHost('https://your-instance.tweakwise.com');

// Create an API instance
$navigationApi = new NavigationApi(null, $config);

try {
    // Make API calls
    $result = $navigationApi->getNavigation([
        'tn-key' => 'your-tweakwise-instance-key',
        'categoryId' => '12345'
    ]);
    
    echo "Navigation items: " . count($result->getItems()) . "\n";
} catch (Exception $e) {
    echo 'Exception: ', $e->getMessage(), "\n";
}
```

## Guzzle Usage

If you prefer to use a specific Guzzle HTTP client, you can pass it to the API constructor:

```php
<?php
require_once 'vendor/autoload.php';

use GuzzleHttp\Client;
use Http\Adapter\Guzzle7\Client as GuzzleAdapter;
use Toppy\TweakwiseClient\Configuration;
use Toppy\TweakwiseClient\Api\NavigationApi;

// Create a Guzzle client with custom configuration
$guzzleClient = new Client([
    'timeout' => 30,
    'verify' => true,
    'headers' => [
        'User-Agent' => 'MyApp/1.0'
    ]
]);

// Wrap it in an HTTPlug adapter
$httpClient = new GuzzleAdapter($guzzleClient);

// Configure the Tweakwise client
$config = Configuration::getDefaultConfiguration();
$config->setApiKey('tn-key', 'your-tweakwise-instance-key');
$config->setHost('https://your-instance.tweakwise.com');

// Create API instance with custom HTTP client
$navigationApi = new NavigationApi($httpClient, $config);

try {
    $result = $navigationApi->getNavigation([
        'tn-key' => 'your-tweakwise-instance-key',
        'categoryId' => '12345'
    ]);
    
    echo "Navigation items: " . count($result->getItems()) . "\n";
} catch (Exception $e) {
    echo 'Exception: ', $e->getMessage(), "\n";
}
```

## Symfony HTTP Client Usage

You can also use the Symfony HTTP Client with this library:

```php
<?php
require_once 'vendor/autoload.php';

use Symfony\Component\HttpClient\HttpClient;
use Symfony\Component\HttpClient\Psr18Client;
use Toppy\TweakwiseClient\Configuration;
use Toppy\TweakwiseClient\Api\NavigationApi;

// Create a Symfony HTTP client with custom configuration
$symfonyClient = HttpClient::create([
    'timeout' => 30,
    'max_redirects' => 3,
    'headers' => [
        'User-Agent' => 'MyApp/1.0'
    ]
]);

// Wrap it in a PSR-18 compatible client
$httpClient = new Psr18Client($symfonyClient);

// Configure the Tweakwise client
$config = Configuration::getDefaultConfiguration();
$config->setApiKey('tn-key', 'your-tweakwise-instance-key');
$config->setHost('https://your-instance.tweakwise.com');

// Create API instance with Symfony HTTP client
$navigationApi = new NavigationApi($httpClient, $config);

try {
    $result = $navigationApi->getNavigation([
        'tn-key' => 'your-tweakwise-instance-key',
        'categoryId' => '12345'
    ]);
    
    echo "Navigation items: " . count($result->getItems()) . "\n";
} catch (Exception $e) {
    echo 'Exception: ', $e->getMessage(), "\n";
}
```

## Available APIs

The client provides access to all Tweakwise API endpoints:

- **NavigationApi** - Category navigation and filtering
- **SearchApi** - Product search functionality  
- **AutocompleteApi** - Search suggestions and autocomplete
- **RecommendationsApi** - Product recommendations
- **CatalogApi** - Catalog management
- **FacetsApi** - Faceted search attributes
- And many more...

## Documentation

For detailed API documentation, examples, and model definitions, see the [docs](./docs/) folder:

- [API Documentation](./docs/Api/) - Complete API reference
- [Model Documentation](./docs/Model/) - Data model definitions

## Authentication

All API calls require authentication using your Tweakwise instance key. The key should be passed as the `tn-key` parameter in API requests.

## License

This project is licensed under the MIT License.