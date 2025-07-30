# Toppy\TweakwiseClient\SearchbannersApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**searchbanners()**](SearchbannersApi.md#searchbanners) | **GET** /searchbanners/{instancekey} | searchbanners


## `searchbanners()`

```php
searchbanners($instancekey, $tnQ, $tWNSource, $tnCid, $tnKeyboard): \Toppy\TweakwiseClient\Model\SearchBanner[]
```

searchbanners

Service that returns searchbanners based on a search term.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\SearchbannersApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*

try {
    $result = $apiInstance->searchbanners($instancekey, $tnQ, $tWNSource, $tnCid, $tnKeyboard);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SearchbannersApi->searchbanners: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tnQ** | **string**| Search term entered by the user. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\SearchBanner[]**](../Model/SearchBanner.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
