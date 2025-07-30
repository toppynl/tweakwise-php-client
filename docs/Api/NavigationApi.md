# Toppy\TweakwiseClient\NavigationApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**navigation()**](NavigationApi.md#navigation) | **GET** /navigation/{instancekey} | Navigation
[**navigationGrouped()**](NavigationApi.md#navigationGrouped) | **GET** /navigation/grouped/{instancekey} | Grouped navigation


## `navigation()`

```php
navigation($instancekey, $tWNSource, $tnCid, $tnUseFilters, $tnFilters, $tnSort, $tnP, $tnPs, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnOptions): \Toppy\TweakwiseClient\Model\Navigation
```

Navigation

Service that returns all the required information for navigating through products.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\NavigationApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnUseFilters = True; // bool | Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters=brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand=Coca%20Cola&tn_fk_volume=1L).   *Example: ?tn_use_filters=true*
$tnFilters = 'tnFilters_example'; // string | A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_filters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_filters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnSort = 'tnSort_example'; // string | Sorting the results. The XML returns the values which can be used for sorting. Descending sorting (DESC) is indicated with a - before the value.   *Example: ?tn_sort=-name*
$tnP = 3.4; // float | The page number of the page that must be displayed.   *Example: ?tn_p=14*
$tnPs = 3.4; // float | The number of products that must be displayed per page. The standard value is configured at shop level. Only use this parameter to overrule this standard configured quantity.   *Example: ?tn_ps=25*
$tnFt = 3.4; // float | Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft=2*
$tnSt = 3.4; // float | Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st=4*
$tnB = 3.4; // float | Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &tn_b=8*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*
$tnOptions = array('tnOptions_example'); // string[] | A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\", \"?tn_options=NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\", \"?tn_options=NoEDC

try {
    $result = $apiInstance->navigation($instancekey, $tWNSource, $tnCid, $tnUseFilters, $tnFilters, $tnSort, $tnP, $tnPs, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnOptions);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NavigationApi->navigation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnUseFilters** | **bool**| Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters&#x3D;brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand&#x3D;Coca%20Cola&amp;tn_fk_volume&#x3D;1L).   *Example: ?tn_use_filters&#x3D;true* | [optional]
 **tnFilters** | **string**| A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_filters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_filters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnSort** | **string**| Sorting the results. The XML returns the values which can be used for sorting. Descending sorting (DESC) is indicated with a - before the value.   *Example: ?tn_sort&#x3D;-name* | [optional]
 **tnP** | **float**| The page number of the page that must be displayed.   *Example: ?tn_p&#x3D;14* | [optional]
 **tnPs** | **float**| The number of products that must be displayed per page. The standard value is configured at shop level. Only use this parameter to overrule this standard configured quantity.   *Example: ?tn_ps&#x3D;25* | [optional]
 **tnFt** | **float**| Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft&#x3D;2* | [optional]
 **tnSt** | **float**| Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st&#x3D;4* | [optional]
 **tnB** | **float**| Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &amp;tn_b&#x3D;8* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]
 **tnOptions** | [**string[]**](../Model/string.md)| A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\&quot;, \&quot;?tn_options&#x3D;NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\&quot;, \&quot;?tn_options&#x3D;NoEDC | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Navigation**](../Model/Navigation.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `navigationGrouped()`

```php
navigationGrouped($instancekey, $tWNSource, $tnCid, $tnUseFilters, $tnFilters, $tnSort, $tnP, $tnPs, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnOptions): \Toppy\TweakwiseClient\Model\NavigationGrouped
```

Grouped navigation

Service that returns all the required grouped information for navigating through products.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\NavigationApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnUseFilters = True; // bool | Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters=brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand=Coca%20Cola&tn_fk_volume=1L).   *Example: ?tn_use_filters=true*
$tnFilters = 'tnFilters_example'; // string | A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_filters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_filters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnSort = 'tnSort_example'; // string | Sorting the results. The XML returns the values which can be used for sorting. Descending sorting (DESC) is indicated with a - before the value.   *Example: ?tn_sort=-name*
$tnP = 3.4; // float | The page number of the page that must be displayed.   *Example: ?tn_p=14*
$tnPs = 3.4; // float | The number of products that must be displayed per page. The standard value is configured at shop level. Only use this parameter to overrule this standard configured quantity.   *Example: ?tn_ps=25*
$tnFt = 3.4; // float | Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft=2*
$tnSt = 3.4; // float | Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st=4*
$tnB = 3.4; // float | Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &tn_b=8*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*
$tnOptions = array('tnOptions_example'); // string[] | A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\", \"?tn_options=NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\", \"?tn_options=NoEDC

try {
    $result = $apiInstance->navigationGrouped($instancekey, $tWNSource, $tnCid, $tnUseFilters, $tnFilters, $tnSort, $tnP, $tnPs, $tnFt, $tnSt, $tnB, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnOptions);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NavigationApi->navigationGrouped: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnUseFilters** | **bool**| Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters&#x3D;brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand&#x3D;Coca%20Cola&amp;tn_fk_volume&#x3D;1L).   *Example: ?tn_use_filters&#x3D;true* | [optional]
 **tnFilters** | **string**| A list of key/value pairs of the filters that should be applied. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_filters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_filters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnSort** | **string**| Sorting the results. The XML returns the values which can be used for sorting. Descending sorting (DESC) is indicated with a - before the value.   *Example: ?tn_sort&#x3D;-name* | [optional]
 **tnP** | **float**| The page number of the page that must be displayed.   *Example: ?tn_p&#x3D;14* | [optional]
 **tnPs** | **float**| The number of products that must be displayed per page. The standard value is configured at shop level. Only use this parameter to overrule this standard configured quantity.   *Example: ?tn_ps&#x3D;25* | [optional]
 **tnFt** | **float**| Explicitly specify the ID of the filter template to use. This will overrule any filter template that would otherwise be applied.   *Example: ?tn_ft&#x3D;2* | [optional]
 **tnSt** | **float**| Explicitly specify the ID of the sorting template to use. This will overrule any sorting template that would otherwise be applied.   *Example: ?tn_st&#x3D;4* | [optional]
 **tnB** | **float**| Explicitly specify the ID of the builder to use. This will overrule any builder that would otherwise be applied.   *Example: &amp;tn_b&#x3D;8* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]
 **tnOptions** | [**string[]**](../Model/string.md)| A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\&quot;, \&quot;?tn_options&#x3D;NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\&quot;, \&quot;?tn_options&#x3D;NoEDC | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\NavigationGrouped**](../Model/NavigationGrouped.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
