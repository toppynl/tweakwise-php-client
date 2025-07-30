# Toppy\TweakwiseClient\FeedApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**feed()**](FeedApi.md#feed) | **GET** /feed/{instancekey}/{profileKey} | Feed


## `feed()`

```php
feed($instancekey, $profileKey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept): \Toppy\TweakwiseClient\Model\Feed
```

Feed

Service that returns all the required information for a personal Feed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\FeedApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$profileKey = 'profileKey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ff106b0a-b5bf-43fc-945c-318f17cda425*
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*

try {
    $result = $apiInstance->feed($instancekey, $profileKey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FeedApi->feed: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **profileKey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ff106b0a-b5bf-43fc-945c-318f17cda425* |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Feed**](../Model/Feed.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
