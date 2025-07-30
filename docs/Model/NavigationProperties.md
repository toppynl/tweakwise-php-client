# # NavigationProperties

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**nrofitems** | **int** | Total number of items | [optional]
**pagesize** | **int** | Number of items per page | [optional]
**nrofpages** | **int** | Total number of pages | [optional]
**currentpage** | **int** | Current selected page | [optional]
**selectedcategory** | **int** | Selected category | [optional]
**selectedcategorykey** | **string** | Selected category key. In case of alphanumeric category identifiers, this field will be populated with the category key. In case of numeric category id&#39;s, this field will be populated with the category id. | [optional]
**searchterm** | **string** | Current search term | [optional]
**suggestedsearchterm** | **string** | Suggested search term | [optional]
**isdirectsearch** | **bool** | true/false to indicate if it&#39;s a direct search. It&#39;s true when: it&#39;s a search page, 1 category is selected and sort options isn&#39;t active. | [optional]
**isrootcategory** | **bool** | true/false to indicate if the current category is the root category | [optional]
**pageurl** | **string** | Current page URL without pagination | [optional]
**reseturl** | **string** | URL to reset all filters | [optional]
**sortfields** | [**\Toppy\TweakwiseClient\Model\NavigationSortfield[]**](NavigationSortfield.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
