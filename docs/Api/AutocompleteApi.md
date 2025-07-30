# Toppy\TweakwiseClient\AutocompleteApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**autocomplete()**](AutocompleteApi.md#autocomplete) | **GET** /autocomplete/{instancekey} | Autocomplete
[**autocompleteGrouped()**](AutocompleteApi.md#autocompleteGrouped) | **GET** /autocomplete/grouped/{instancekey} | Grouped autocomplete


## `autocomplete()`

```php
autocomplete($instancekey, $tnQ, $tWNSource, $tnCid, $tnItems, $tnSuggestions, $tnInstant, $tnMaxresults, $tnLang, $tnKeyboard, $tnParameters, $tnParametersExcept, $tnOptions): \Toppy\TweakwiseClient\Model\Autocomplete
```

Autocomplete

Service that returns product results and search suggestions based on a search term. This service can be called as soon as the user begins to type a search term.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\AutocompleteApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnItems = True; // bool | Display product suggestions.   *Default value: true*
$tnSuggestions = True; // bool | Display keyword suggestions.   *Default value: true*
$tnInstant = True; // bool | Use instant search.   *Default value: false*
$tnMaxresults = 3.4; // float | The number of results that will be returned per component.   *Default value: 6*  *Maximum value: 20*
$tnLang = 'tnLang_example'; // string | Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang=nl*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnOptions = array('tnOptions_example'); // string[] | A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\", \"?tn_options=NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\", \"?tn_options=NoEDC

try {
    $result = $apiInstance->autocomplete($instancekey, $tnQ, $tWNSource, $tnCid, $tnItems, $tnSuggestions, $tnInstant, $tnMaxresults, $tnLang, $tnKeyboard, $tnParameters, $tnParametersExcept, $tnOptions);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutocompleteApi->autocomplete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnItems** | **bool**| Display product suggestions.   *Default value: true* | [optional]
 **tnSuggestions** | **bool**| Display keyword suggestions.   *Default value: true* | [optional]
 **tnInstant** | **bool**| Use instant search.   *Default value: false* | [optional]
 **tnMaxresults** | **float**| The number of results that will be returned per component.   *Default value: 6*  *Maximum value: 20* | [optional]
 **tnLang** | **string**| Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang&#x3D;nl* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnOptions** | [**string[]**](../Model/string.md)| A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\&quot;, \&quot;?tn_options&#x3D;NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\&quot;, \&quot;?tn_options&#x3D;NoEDC | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Autocomplete**](../Model/Autocomplete.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `autocompleteGrouped()`

```php
autocompleteGrouped($instancekey, $tnQ, $tWNSource, $tnCid, $tnItems, $tnSuggestions, $tnInstant, $tnMaxresults, $tnLang, $tnKeyboard, $tnParameters, $tnParametersExcept, $tnOptions): \Toppy\TweakwiseClient\Model\AutocompleteGrouped
```

Grouped autocomplete

Service that returns grouped product results and grouped search suggestions based on a search term. This service can be called as soon as the user begins to type a search term.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\AutocompleteApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$tnQ = 'tnQ_example'; // string | Search term entered by the user.   *Maximum length: 100*
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$tnCid = 'tnCid_example'; // string | The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid=100-150*
$tnItems = True; // bool | Display product suggestions.   *Default value: true*
$tnSuggestions = True; // bool | Display keyword suggestions.   *Default value: true*
$tnInstant = True; // bool | Use instant search.   *Default value: false*
$tnMaxresults = 3.4; // float | The number of results that will be returned per component.   *Default value: 6*  *Maximum value: 20*
$tnLang = 'tnLang_example'; // string | Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang=nl*
$tnKeyboard = 'tnKeyboard_example'; // string | Specify the keyboard to use for the search algorithms.  All available options are: 'qwerty', 'azerty' or 'qwertz'   *Example: ?tn_keyboard=azerty*
$tnParameters = 'tnParameters_example'; // string | Hidden parameters can be added to the URL by using the parameter 'tn_parameters'. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property 'brand' with value 'Coca Cola' or 'Pepsi' and 'volume' 1L or 1.5L, the value of tn_parameters should be: brand=Coca Cola|Pepsi&volume=1L|1.5L  *Example: ?tn_parameters=brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L*
$tnParametersExcept = 'tnParametersExcept_example'; // string | Hidden exclusion parameters can be added to the URL by using the parameter 'tn_parameters_except'.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property 'brand' with value 'Coca Cola' or with value 'Pepsi' the value of tn_parameters_except should be: brand=Coca Cola&brand=Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except=brand%3DCoca%20Cola%26brand%3DPepsi*
$tnOptions = array('tnOptions_example'); // string[] | A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\", \"?tn_options=NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\", \"?tn_options=NoEDC

try {
    $result = $apiInstance->autocompleteGrouped($instancekey, $tnQ, $tWNSource, $tnCid, $tnItems, $tnSuggestions, $tnInstant, $tnMaxresults, $tnLang, $tnKeyboard, $tnParameters, $tnParametersExcept, $tnOptions);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutocompleteApi->autocompleteGrouped: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **tnQ** | **string**| Search term entered by the user.   *Maximum length: 100* |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **tnCid** | **string**| The category that should contain the filtered results. If you want to provide the entire path, you should include the categories divided by a hyphen (-).   *Example: ?tn_cid&#x3D;100-150* | [optional]
 **tnItems** | **bool**| Display product suggestions.   *Default value: true* | [optional]
 **tnSuggestions** | **bool**| Display keyword suggestions.   *Default value: true* | [optional]
 **tnInstant** | **bool**| Use instant search.   *Default value: false* | [optional]
 **tnMaxresults** | **float**| The number of results that will be returned per component.   *Default value: 6*  *Maximum value: 20* | [optional]
 **tnLang** | **string**| Specify the language to use for the search algorithms.  All available languages can be retrieved with the catalog call: /catalog/languages/{instancekey}   *Example: ?tn_lang&#x3D;nl* | [optional]
 **tnKeyboard** | **string**| Specify the keyboard to use for the search algorithms.  All available options are: &#39;qwerty&#39;, &#39;azerty&#39; or &#39;qwertz&#39;   *Example: ?tn_keyboard&#x3D;azerty* | [optional]
 **tnParameters** | **string**| Hidden parameters can be added to the URL by using the parameter &#39;tn_parameters&#39;. The key is the facet URL-name. The value is the facet value that should be applied. When using multiple values they should be separated using a pipe (|).  When filtering drinks by property &#39;brand&#39; with value &#39;Coca Cola&#39; or &#39;Pepsi&#39; and &#39;volume&#39; 1L or 1.5L, the value of tn_parameters should be: brand&#x3D;Coca Cola|Pepsi&amp;volume&#x3D;1L|1.5L  *Example: ?tn_parameters&#x3D;brand%3DCoca%20Cola%7CPepsi%26volume%3D1L%7C1.5L* | [optional]
 **tnParametersExcept** | **string**| Hidden exclusion parameters can be added to the URL by using the parameter &#39;tn_parameters_except&#39;.  This is used to exclude certain parameters from the results (show everything except specified parameters)  When filtering by property &#39;brand&#39; with value &#39;Coca Cola&#39; or with value &#39;Pepsi&#39; the value of tn_parameters_except should be: brand&#x3D;Coca Cola&amp;brand&#x3D;Pepsi  This value should then be URL encoded.  *Example: ?tn_parameters_except&#x3D;brand%3DCoca%20Cola%26brand%3DPepsi* | [optional]
 **tnOptions** | [**string[]**](../Model/string.md)| A comma-separated list of toggles.  - NoBuilder: Prevents the configured builder from being applied; handles the request as if no builder were configured.\&quot;, \&quot;?tn_options&#x3D;NoBuilder - NoEDC: Prevents calls to External Data Components configured in builders; handles the request as if no External Data Components were configured.\&quot;, \&quot;?tn_options&#x3D;NoEDC | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\AutocompleteGrouped**](../Model/AutocompleteGrouped.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
