# Toppy\TweakwiseClient\InstanceApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**instance()**](InstanceApi.md#instance) | **GET** /instance/{instancekey} | Instance


## `instance()`

```php
instance($instancekey, $tWNSource): \Toppy\TweakwiseClient\Model\Instance
```

Instance

Endpoint that returns some instance configuration

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\InstanceApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.

try {
    $result = $apiInstance->instance($instancekey, $tWNSource);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstanceApi->instance: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Instance**](../Model/Instance.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
