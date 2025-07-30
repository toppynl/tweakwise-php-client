# Toppy\TweakwiseClient\VisualSearchApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**visualsearch()**](VisualSearchApi.md#visualsearch) | **POST** /visual-search/{instancekey} | VisualSearch
[**visualsearchGrouped()**](VisualSearchApi.md#visualsearchGrouped) | **POST** /visual-search/grouped/{instancekey} | Grouped VisualSearch


## `visualsearch()`

```php
visualsearch($instancekey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $imageFile)
```

VisualSearch

Service that returns all the required information for productsearch based on an image.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\VisualSearchApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$imageFile = '/path/to/file.txt'; // \SplFileObject

try {
    $apiInstance->visualsearch($instancekey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $imageFile);
} catch (Exception $e) {
    echo 'Exception when calling VisualSearchApi->visualsearch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **imageFile** | **\SplFileObject****\SplFileObject**|  | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `text/xml`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `visualsearchGrouped()`

```php
visualsearchGrouped($instancekey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $imageFile)
```

Grouped VisualSearch

Service that returns all the grouped required information for productsearch based on an image.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\VisualSearchApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$imageFile = '/path/to/file.txt'; // \SplFileObject

try {
    $apiInstance->visualsearchGrouped($instancekey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $imageFile);
} catch (Exception $e) {
    echo 'Exception when calling VisualSearchApi->visualsearchGrouped: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **imageFile** | **\SplFileObject****\SplFileObject**|  | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `text/xml`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
