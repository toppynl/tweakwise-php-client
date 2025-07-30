# Toppy\TweakwiseClient\SuggestionsApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**suggestions()**](SuggestionsApi.md#suggestions) | **GET** /suggestions/{instancekey} | Suggestions
[**suggestionsGrouped()**](SuggestionsApi.md#suggestionsGrouped) | **GET** /suggestions/grouped/{instancekey} | Suggestions grouped
[**suggestionsProducts()**](SuggestionsApi.md#suggestionsProducts) | **GET** /suggestions/products/{instancekey} | Suggestion products
[**suggestionsProductsGrouped()**](SuggestionsApi.md#suggestionsProductsGrouped) | **GET** /suggestions/products/grouped/{instancekey} | Suggestion products grouped


## `suggestions()`

```php
suggestions($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnUseFilters, $tnParameters, $tnParametersExcept, $tnKeyboard): \Toppy\TweakwiseClient\Model\SuggestionGroup[]
```

Suggestions

Service that returns search suggestions based on a search term. This service can be called as soon as the user begins to type a search term.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\SuggestionsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnLang = 'tnLang_example'; // string | Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang=nl*
$tnUseFilters = True; // bool | Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters=brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand=Coca%20Cola&tn_fk_volume=1L).   *Example: ?tn_use_filters=true*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*

try {
    $result = $apiInstance->suggestions($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnUseFilters, $tnParameters, $tnParametersExcept, $tnKeyboard);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuggestionsApi->suggestions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* |
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnLang** | **string**| Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang&#x3D;nl* | [optional]
 **tnUseFilters** | **bool**| Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters&#x3D;brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand&#x3D;Coca%20Cola&amp;tn_fk_volume&#x3D;1L).   *Example: ?tn_use_filters&#x3D;true* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\SuggestionGroup[]**](../Model/SuggestionGroup.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `suggestionsGrouped()`

```php
suggestionsGrouped($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnUseFilters, $tnParameters, $tnParametersExcept, $tnKeyboard): \Toppy\TweakwiseClient\Model\SuggestionGroup[]
```

Suggestions grouped

Service that returns search suggestions based on a search term. This service can be called as soon as the user begins to type a search term.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\SuggestionsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnLang = 'tnLang_example'; // string | Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang=nl*
$tnUseFilters = True; // bool | Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters=brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand=Coca%20Cola&tn_fk_volume=1L).   *Example: ?tn_use_filters=true*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*

try {
    $result = $apiInstance->suggestionsGrouped($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnUseFilters, $tnParameters, $tnParametersExcept, $tnKeyboard);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuggestionsApi->suggestionsGrouped: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* |
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnLang** | **string**| Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang&#x3D;nl* | [optional]
 **tnUseFilters** | **bool**| Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters&#x3D;brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand&#x3D;Coca%20Cola&amp;tn_fk_volume&#x3D;1L).   *Example: ?tn_use_filters&#x3D;true* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\SuggestionGroup[]**](../Model/SuggestionGroup.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `suggestionsProducts()`

```php
suggestionsProducts($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnKeyboard, $tnOptions): \Toppy\TweakwiseClient\Model\Suggestions
```

Suggestion products

Service that returns product results based on a search term. This service can be called as soon as the user begins to type a search term.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\SuggestionsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnLang = 'tnLang_example'; // string | Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang=nl*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*
$tnOptions = array('tnOptions_example'); // string[] | A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\", \"?tn_options=NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\", \"?tn_options=NoEDC

try {
    $result = $apiInstance->suggestionsProducts($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnKeyboard, $tnOptions);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuggestionsApi->suggestionsProducts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* |
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnLang** | **string**| Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang&#x3D;nl* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]
 **tnOptions** | [**string[]**](../Model/string.md)| A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\&quot;, \&quot;?tn_options&#x3D;NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\&quot;, \&quot;?tn_options&#x3D;NoEDC | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Suggestions**](../Model/Suggestions.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `suggestionsProductsGrouped()`

```php
suggestionsProductsGrouped($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnKeyboard, $tnOptions): \Toppy\TweakwiseClient\Model\SuggestionsGrouped
```

Suggestion products grouped

Service that returns product suggestions (grouped) based on a search term. This service can be called as soon as the user begins to type a search term.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\SuggestionsApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnLang = 'tnLang_example'; // string | Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang=nl*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnProfilekey = 'tnProfilekey_example'; // string | The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey=ff106b0a-b5bf-43fc-945c-318f17cda425*
$tnEdcParameters = 'tnEdcParameters_example'; // string | Extra parameters for external data components can be added to the URL by using the parameter 'tn_edc_parameters'.  For example, to send 2 extra parameters: 'firstParameter' and 'secondParameter' to external data components, using the following string: firstParameter=firstValue&secondParameter=secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters=firstParameter%3DfirstValue%26secondParameter%3DsecondValue*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*
$tnOptions = array('tnOptions_example'); // string[] | A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\", \"?tn_options=NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\", \"?tn_options=NoEDC

try {
    $result = $apiInstance->suggestionsProductsGrouped($instancekey, $tnQ, $tnCid, $tWNSource, $tnLang, $tnParameters, $tnParametersExcept, $tnProfilekey, $tnEdcParameters, $tnKeyboard, $tnOptions);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuggestionsApi->suggestionsProductsGrouped: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* |
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnLang** | **string**| Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang&#x3D;nl* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnProfilekey** | **string**| The profile key is an identifier for the person browsing your website who is initiating the navigation requests. This same identifier should also be used to identify the visitor when sending events to our Analytics API. Based on the sent events, the visitor can receive personalized results.  The profile key can be any string as long as it is unique to the visitor. Generate for example a Universally Unique Identifier (UUID), a new id per visitor or use an account id.   *Example: ?tn_profilekey&#x3D;ff106b0a-b5bf-43fc-945c-318f17cda425* | [optional]
 **tnEdcParameters** | **string**| Extra parameters for external data components can be added to the URL by using the parameter &#39;tn_edc_parameters&#39;.  For example, to send 2 extra parameters: &#39;firstParameter&#39; and &#39;secondParameter&#39; to external data components, using the following string: firstParameter&#x3D;firstValue&amp;secondParameter&#x3D;secondValue  This value should then be URL encoded.  *Example: ?tn_edc_parameters&#x3D;firstParameter%3DfirstValue%26secondParameter%3DsecondValue* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]
 **tnOptions** | [**string[]**](../Model/string.md)| A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\&quot;, \&quot;?tn_options&#x3D;NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\&quot;, \&quot;?tn_options&#x3D;NoEDC | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\SuggestionsGrouped**](../Model/SuggestionsGrouped.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
