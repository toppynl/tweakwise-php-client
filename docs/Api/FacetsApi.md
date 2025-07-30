# Toppy\TweakwiseClient\FacetsApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**facetAttributes()**](FacetsApi.md#facetAttributes) | **GET** /facets/{urlkey}/attributes/{instancekey} | Facet attributes
[**facets()**](FacetsApi.md#facets) | **GET** /facets/{instancekey} | Facets


## `facetAttributes()`

```php
facetAttributes($instancekey, $urlkey, $tWNSource, $tnQ, $tnCid, $tnUseFilters, $tnFilters, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnKeyboard, $tnProfilekey): \Toppy\TweakwiseClient\Model\FacetAttributesResponse
```

Facet attributes

Service that returns only the attributes of the specified facet.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\FacetsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$urlkey = 'urlkey_example'; // string | The url key of the facet attribute.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnUseFilters = True; // bool | Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters=brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand=Coca%20Cola&tn_fk_volume=1L).   *Example: ?tn_use_filters=true*
$tnFilters = 'tnFilters_example'; // string | A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_filters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_filters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnFt = 3.4; // float | Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft=2*
$tnSt = 3.4; // float | Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st=4*
$tnB = 3.4; // float | Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &tn_b=8*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*

try {
    $result = $apiInstance->facetAttributes($instancekey, $urlkey, $tWNSource, $tnQ, $tnCid, $tnUseFilters, $tnFilters, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnKeyboard, $tnProfilekey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FacetsApi->facetAttributes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **urlkey** | **string**| The url key of the facet attribute. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnUseFilters** | **bool**| Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters&#x3D;brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand&#x3D;Coca%20Cola&amp;tn_fk_volume&#x3D;1L).   *Example: ?tn_use_filters&#x3D;true* | [optional]
 **tnFilters** | **string**| A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_filters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_filters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnFt** | **float**| Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft&#x3D;2* | [optional]
 **tnSt** | **float**| Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st&#x3D;4* | [optional]
 **tnB** | **float**| Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &amp;tn_b&#x3D;8* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\FacetAttributesResponse**](../Model/FacetAttributesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `facets()`

```php
facets($instancekey, $tWNSource, $tnQ, $tnCid, $tnUseFilters, $tnFilters, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnKeyboard, $tnProfilekey): \Toppy\TweakwiseClient\Model\FacetsResponse
```

Facets

Service that returns only the facets and visible attributes for a request. This request is the same as the navigation request, but without the products. Only the visible facet attributes will be returned, based on nrofshownattributes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\FacetsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnUseFilters = True; // bool | Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters=brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand=Coca%20Cola&tn_fk_volume=1L).   *Example: ?tn_use_filters=true*
$tnFilters = 'tnFilters_example'; // string | A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_filters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_filters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnFt = 3.4; // float | Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft=2*
$tnSt = 3.4; // float | Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st=4*
$tnB = 3.4; // float | Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &tn_b=8*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*

try {
    $result = $apiInstance->facets($instancekey, $tWNSource, $tnQ, $tnCid, $tnUseFilters, $tnFilters, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnKeyboard, $tnProfilekey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FacetsApi->facets: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnUseFilters** | **bool**| Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters&#x3D;brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand&#x3D;Coca%20Cola&amp;tn_fk_volume&#x3D;1L).   *Example: ?tn_use_filters&#x3D;true* | [optional]
 **tnFilters** | **string**| A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_filters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_filters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnFt** | **float**| Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft&#x3D;2* | [optional]
 **tnSt** | **float**| Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st&#x3D;4* | [optional]
 **tnB** | **float**| Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &amp;tn_b&#x3D;8* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\FacetsResponse**](../Model/FacetsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
