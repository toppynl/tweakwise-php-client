# Toppy\TweakwiseClient\RecommendationsApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**featuredRecommendations()**](RecommendationsApi.md#featuredRecommendations) | **GET** /recommendations/featured/{instancekey}/{displayId} | Featured products
[**productRecommendationsAll()**](RecommendationsApi.md#productRecommendationsAll) | **GET** /recommendations/product/{instancekey}/{productNo} | Product recommendations
[**productRecommendationsSingle()**](RecommendationsApi.md#productRecommendationsSingle) | **GET** /recommendations/product/{instancekey}/{productRecId}/{productNo} | Product recommendations single rule
[**productRecommendationsSingleGrouped()**](RecommendationsApi.md#productRecommendationsSingleGrouped) | **GET** /recommendations/grouped/{instancekey}/{productNo}/{groupKey} | Product recommendations multi rule


## `featuredRecommendations()`

```php
featuredRecommendations($instancekey, $displayId, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters): \Toppy\TweakwiseClient\Model\FeaturedRecommendations
```

Featured products

Service that returns the featured products based on a key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$displayId = 'displayId_example'; // string | The id of the featured recommendation.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*

try {
    $result = $apiInstance->featuredRecommendations($instancekey, $displayId, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->featuredRecommendations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **displayId** | **string**| The id of the featured recommendation. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\FeaturedRecommendations**](../Model/FeaturedRecommendations.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `productRecommendationsAll()`

```php
productRecommendationsAll($instancekey, $productNo, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters): \Toppy\TweakwiseClient\Model\ProductRecommendations
```

Product recommendations

Service that returns all recommended products of a product for all rules.  If a lot of rules have been set up, it is not efficient to request all rules for all products. With these web services, all products of a product can be retrieved in one go for all rules.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$productNo = 'productNo_example'; // string | Product (article number) for which up and cross selling must be retrieved on the basis of the indicated rule.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*

try {
    $result = $apiInstance->productRecommendationsAll($instancekey, $productNo, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->productRecommendationsAll: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **productNo** | **string**| Product (article number) for which up and cross selling must be retrieved on the basis of the indicated rule. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\ProductRecommendations**](../Model/ProductRecommendations.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `productRecommendationsSingle()`

```php
productRecommendationsSingle($instancekey, $productRecId, $productNo, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters): \Toppy\TweakwiseClient\Model\ProductRecommendation
```

Product recommendations single rule

Service that returns the collection of up and cross selling for a product, based on a single rule.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$productRecId = 'productRecId_example'; // string | The ID of the up and cross selling rule.
$productNo = 'productNo_example'; // string | Product (article number) for which up and cross selling must be retrieved on the basis of the indicated rule.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*

try {
    $result = $apiInstance->productRecommendationsSingle($instancekey, $productRecId, $productNo, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->productRecommendationsSingle: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **productRecId** | **string**| The ID of the up and cross selling rule. |
 **productNo** | **string**| Product (article number) for which up and cross selling must be retrieved on the basis of the indicated rule. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\ProductRecommendation**](../Model/ProductRecommendation.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `productRecommendationsSingleGrouped()`

```php
productRecommendationsSingleGrouped($instancekey, $productNo, $groupKey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters): \Toppy\TweakwiseClient\Model\ProductRecommendationGrouped
```

Product recommendations multi rule

Service that returns the grouped collection of up and cross selling for a product.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$productNo = 'productNo_example'; // string | Product (article number) for which up and cross selling must be retrieved on the basis of the indicated rule.
$groupKey = 'groupKey_example'; // string | This is a tag for a recommendation, which allows the recommendations to be grouped.  All available groups and their group keys can be retrieved with the catalog call: /catalog/recommendation/product/groups/{instancekey}.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*

try {
    $result = $apiInstance->productRecommendationsSingleGrouped($instancekey, $productNo, $groupKey, $tWNSource, $tnCid, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->productRecommendationsSingleGrouped: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **productNo** | **string**| Product (article number) for which up and cross selling must be retrieved on the basis of the indicated rule. |
 **groupKey** | **string**| This is a tag for a recommendation, which allows the recommendations to be grouped.  All available groups and their group keys can be retrieved with the catalog call: /catalog/recommendation/product/groups/{instancekey}. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\ProductRecommendationGrouped**](../Model/ProductRecommendationGrouped.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
