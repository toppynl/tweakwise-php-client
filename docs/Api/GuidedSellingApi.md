# Toppy\TweakwiseClient\GuidedSellingApi

All URIs are relative to https://gateway.tweakwisenavigator.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**guidedSellingCompare()**](GuidedSellingApi.md#guidedSellingCompare) | **GET** /advisor/{instancekey} | Compare
[**guidedSellingFunnel()**](GuidedSellingApi.md#guidedSellingFunnel) | **GET** /filterwizard/{instancekey} | Funnel


## `guidedSellingCompare()`

```php
guidedSellingCompare($instancekey, $code, $tWNSource, $answers, $tnSkipQs, $ps): \Toppy\TweakwiseClient\Model\Advisor
```

Compare

Service that makes it possible to filter products questioningly and then compare them with each other. The results will be sorted by the most appropriate product.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\GuidedSellingApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$code = 'code_example'; // string | Compare code.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$answers = {"tn_qs_1":"1|2","tn_qs_2":"3"}; // array<string,string> | Answer(s) to questions formatted as key-value pairs.  The key of the question being answered has format `tn_qs_{n}`, where `n` is the ID of the question being answered.  The value contains the ID(s) of the answer(s) to the question. When multiple answers are provided, they should be separated by a pipe (|).   *Example: ?tn_qs_1=1%7C2&tn_qs_2=3*
$tnSkipQs = array(3.4); // float[] | Collection of skipped questions.   *Example: ?tn_skip_qs=2%2C4%2C6 or ?tn_skip_qs=2&tn_skip_qs=4&tn_skip_qs=6*
$ps = 3.4; // float | Page size, amount of desired products   *Default value: 12*  *Maximum value: 100*

try {
    $result = $apiInstance->guidedSellingCompare($instancekey, $code, $tWNSource, $answers, $tnSkipQs, $ps);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GuidedSellingApi->guidedSellingCompare: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **code** | **string**| Compare code. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **answers** | [**array<string,string>**](../Model/string.md)| Answer(s) to questions formatted as key-value pairs.  The key of the question being answered has format &#x60;tn_qs_{n}&#x60;, where &#x60;n&#x60; is the ID of the question being answered.  The value contains the ID(s) of the answer(s) to the question. When multiple answers are provided, they should be separated by a pipe (|).   *Example: ?tn_qs_1&#x3D;1%7C2&amp;tn_qs_2&#x3D;3* | [optional]
 **tnSkipQs** | [**float[]**](../Model/float.md)| Collection of skipped questions.   *Example: ?tn_skip_qs&#x3D;2%2C4%2C6 or ?tn_skip_qs&#x3D;2&amp;tn_skip_qs&#x3D;4&amp;tn_skip_qs&#x3D;6* | [optional]
 **ps** | **float**| Page size, amount of desired products   *Default value: 12*  *Maximum value: 100* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\Advisor**](../Model/Advisor.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `guidedSellingFunnel()`

```php
guidedSellingFunnel($instancekey, $code, $tWNSource, $catid, $answers, $skipQs, $take, $skip, $tnUseFilters): \Toppy\TweakwiseClient\Model\FilterWizard
```

Funnel

Service that makes it possible to filter the products questioningly and only the products that meet the filter values will be shown. The result contains the questions with their answers and products which are the result of the selected answers. Additionally a navigation url is provided to go to a navigation page with selected filters for the funnel with selected answers.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Toppy\TweakwiseClient\Api\GuidedSellingApi(
    // If you want use custom http client, pass your client which implements `Psr\Http\Client\ClientInterface`.
    // This is optional, `Psr18ClientDiscovery` will be used to find http client. For instance `GuzzleHttp\Client` implements that interface
    new GuzzleHttp\Client()
);
$instancekey = 'instancekey_example'; // string | Instance specific key.
$code = 'code_example'; // string | Funnel code.
$tWNSource = 'tWNSource_example'; // string | The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information.
$catid = 3.4; // float | The category which must contain the results found.   *Example: ?catid=100*
$answers = {"qs1":"1,2","qs2":"3"}; // array<string,string> | Answer(s) to questions formatted as key-value pairs.  The key of the question being answered has format `qs{n}`, where `n` is the ID of the question being answered.  The value contains the ID(s) of the answer(s) to the question. When multiple answers are provided, they should be separated by a comma (,).   *Example: ?qs1=1%2C2&qs2=3*
$skipQs = array(3.4); // float[] | Collection of skipped questions.   *Example: ?skip_qs=2%2C4%2C6 or ?skip_qs=2&skip_qs=4&skip_qs=6*
$take = 3.4; // float | Maximum desired amount of products.
$skip = 3.4; // float | Amount of products to skip (useful for paging).
$tnUseFilters = True; // bool | Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters=brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand=Coca%20Cola&tn_fk_volume=1L).   *Example: ?tn_use_filters=true*

try {
    $result = $apiInstance->guidedSellingFunnel($instancekey, $code, $tWNSource, $catid, $answers, $skipQs, $take, $skip, $tnUseFilters);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GuidedSellingApi->guidedSellingFunnel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **instancekey** | **string**| Instance specific key. |
 **code** | **string**| Funnel code. |
 **tWNSource** | **string**| The source of the request. See [the article on the request source](https://docs.tweakwise.com/reference/request-source) for more information. | [optional]
 **catid** | **float**| The category which must contain the results found.   *Example: ?catid&#x3D;100* | [optional]
 **answers** | [**array<string,string>**](../Model/string.md)| Answer(s) to questions formatted as key-value pairs.  The key of the question being answered has format &#x60;qs{n}&#x60;, where &#x60;n&#x60; is the ID of the question being answered.  The value contains the ID(s) of the answer(s) to the question. When multiple answers are provided, they should be separated by a comma (,).   *Example: ?qs1&#x3D;1%2C2&amp;qs2&#x3D;3* | [optional]
 **skipQs** | [**float[]**](../Model/float.md)| Collection of skipped questions.   *Example: ?skip_qs&#x3D;2%2C4%2C6 or ?skip_qs&#x3D;2&amp;skip_qs&#x3D;4&amp;skip_qs&#x3D;6* | [optional]
 **take** | **float**| Maximum desired amount of products. | [optional]
 **skip** | **float**| Amount of products to skip (useful for paging). | [optional]
 **tnUseFilters** | **bool**| Whether or not navigation urls returned in the response use the tn_filters parameter (?tn_filters&#x3D;brand%3DCoca%20Cola%26volume%3D1L, instead of ?tn_fk_brand&#x3D;Coca%20Cola&amp;tn_fk_volume&#x3D;1L).   *Example: ?tn_use_filters&#x3D;true* | [optional]

### Return type

[**\Toppy\TweakwiseClient\Model\FilterWizard**](../Model/FilterWizard.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
