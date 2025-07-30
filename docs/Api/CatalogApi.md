# Toppy\TweakwiseClient\CatalogApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**catalogBuilders()**](CatalogApi.md#catalogBuilders) | **GET** /catalog/builders/{instancekey} | Builders
[**catalogFeaturedRecommendations()**](CatalogApi.md#catalogFeaturedRecommendations) | **GET** /catalog/recommendation/featured/{instancekey} | Featured recommendations
[**catalogFilterTemplates()**](CatalogApi.md#catalogFilterTemplates) | **GET** /catalog/templates/{instancekey} | Filter templates
[**catalogGuidedSelling()**](CatalogApi.md#catalogGuidedSelling) | **GET** /catalog/guidedselling/{instancekey} | Guided Selling setups
[**catalogProductRecommendations()**](CatalogApi.md#catalogProductRecommendations) | **GET** /catalog/recommendation/product/{instancekey} | Product recommendations
[**catalogProductRecommendationsGroupkeys()**](CatalogApi.md#catalogProductRecommendationsGroupkeys) | **GET** /catalog/recommendation/product/groups/{instancekey} | Product recommendations groups
[**catalogSortingTemplates()**](CatalogApi.md#catalogSortingTemplates) | **GET** /catalog/sorttemplates/{instancekey} | Sorting templates
[**languages()**](CatalogApi.md#languages) | **GET** /catalog/languages/{instancekey} | Languages


## `catalogBuilders()`

```php
catalogBuilders($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\Builder[]
```

Builders

Service that returns all builders.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->catalogBuilders($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->catalogBuilders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Builder[]**](../Model/Builder.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `catalogFeaturedRecommendations()`

```php
catalogFeaturedRecommendations($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\CatalogRecommendationsResponse
```

Featured recommendations

Service that returns featured recommendations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->catalogFeaturedRecommendations($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->catalogFeaturedRecommendations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\CatalogRecommendationsResponse**](../Model/CatalogRecommendationsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `catalogFilterTemplates()`

```php
catalogFilterTemplates($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\CatalogFilterTemplate[]
```

Filter templates

Service that returns filter templates.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->catalogFilterTemplates($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->catalogFilterTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\CatalogFilterTemplate[]**](../Model/CatalogFilterTemplate.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `catalogGuidedSelling()`

```php
catalogGuidedSelling($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\CatalogGuidedSelling[]
```

Guided Selling setups

Service that returns Guided Selling setups.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->catalogGuidedSelling($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->catalogGuidedSelling: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\CatalogGuidedSelling[]**](../Model/CatalogGuidedSelling.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `catalogProductRecommendations()`

```php
catalogProductRecommendations($instancekey, $tWNSource, $tnCid): \Toppy\TweakwiseClient\Model\CatalogRecommendationsResponse
```

Product recommendations

Service that returns the collection of all set up and cross selling rules.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*

try {
    $result = $apiInstance->catalogProductRecommendations($instancekey, $tWNSource, $tnCid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->catalogProductRecommendations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\CatalogRecommendationsResponse**](../Model/CatalogRecommendationsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `catalogProductRecommendationsGroupkeys()`

```php
catalogProductRecommendationsGroupkeys($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\CatalogRecommendationGroup[]
```

Product recommendations groups

Service that returns all the product recommendations groups and their group keys.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->catalogProductRecommendationsGroupkeys($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->catalogProductRecommendationsGroupkeys: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\CatalogRecommendationGroup[]**](../Model/CatalogRecommendationGroup.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `catalogSortingTemplates()`

```php
catalogSortingTemplates($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\CatalogSortTemplate[]
```

Sorting templates

Service that returns sorting templates.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->catalogSortingTemplates($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->catalogSortingTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\CatalogSortTemplate[]**](../Model/CatalogSortTemplate.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `languages()`

```php
languages($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\Language[]
```

Languages

Service that returns all the languages for provided instance.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->languages($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->languages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Language[]**](../Model/Language.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
