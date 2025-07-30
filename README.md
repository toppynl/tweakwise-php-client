# OpenAPIClient-php

Tweakwise API.

Tweakwise offers differing REST services that can be called from various URLs and separate parameters. Response in XML and
JSON format is offered for all services. XML is the default format, JSON format is also possible by adding ‘format=json’ to the call.
Parameters are sent along with the query string (GET Request) via the URL.

---

Authentication

Authentication takes place by means of a unique key valid for each instance.
This key is sent along with the particular service immediately after the call and must be placed before any parameters.
This key is issued by Tweakwise.



## Installation & Usage

### Requirements

PHP 7.2 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/toppynl/tweakwise-php-client.git"
    }
  ],
  "require": {
    "toppynl/tweakwise-php-client": "*@dev"
  }
}
```

Then run `composer install`

Your project is free to choose the http client of your choice
Please require packages that will provide http client functionality:
https://packagist.org/providers/psr/http-client-implementation
https://packagist.org/providers/php-http/async-client-implementation
https://packagist.org/providers/psr/http-factory-implementation

As an example:

```
composer require guzzlehttp/guzzle php-http/guzzle7-adapter http-interop/http-factory-guzzle
```

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/OpenAPIClient-php/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

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

## API Endpoints

All URIs are relative to *https://gateway.tweakwisenavigator.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AutocompleteApi* | [**autocomplete**](docs/Api/AutocompleteApi.md#autocomplete) | **GET** /autocomplete/{instancekey} | Autocomplete
*AutocompleteApi* | [**autocompleteGrouped**](docs/Api/AutocompleteApi.md#autocompletegrouped) | **GET** /autocomplete/grouped/{instancekey} | Grouped autocomplete
*CatalogApi* | [**catalogBuilders**](docs/Api/CatalogApi.md#catalogbuilders) | **GET** /catalog/builders/{instancekey} | Builders
*CatalogApi* | [**catalogFeaturedRecommendations**](docs/Api/CatalogApi.md#catalogfeaturedrecommendations) | **GET** /catalog/recommendation/featured/{instancekey} | Featured recommendations
*CatalogApi* | [**catalogFilterTemplates**](docs/Api/CatalogApi.md#catalogfiltertemplates) | **GET** /catalog/templates/{instancekey} | Filter templates
*CatalogApi* | [**catalogGuidedSelling**](docs/Api/CatalogApi.md#catalogguidedselling) | **GET** /catalog/guidedselling/{instancekey} | Guided Selling setups
*CatalogApi* | [**catalogProductRecommendations**](docs/Api/CatalogApi.md#catalogproductrecommendations) | **GET** /catalog/recommendation/product/{instancekey} | Product recommendations
*CatalogApi* | [**catalogProductRecommendationsGroupkeys**](docs/Api/CatalogApi.md#catalogproductrecommendationsgroupkeys) | **GET** /catalog/recommendation/product/groups/{instancekey} | Product recommendations groups
*CatalogApi* | [**catalogSortingTemplates**](docs/Api/CatalogApi.md#catalogsortingtemplates) | **GET** /catalog/sorttemplates/{instancekey} | Sorting templates
*CatalogApi* | [**languages**](docs/Api/CatalogApi.md#languages) | **GET** /catalog/languages/{instancekey} | Languages
*CategoryTreeApi* | [**categorytree**](docs/Api/CategoryTreeApi.md#categorytree) | **GET** /categorytree/{instancekey} | Category tree
*FacetsApi* | [**facetAttributes**](docs/Api/FacetsApi.md#facetattributes) | **GET** /facets/{urlkey}/attributes/{instancekey} | Facet attributes
*FacetsApi* | [**facets**](docs/Api/FacetsApi.md#facets) | **GET** /facets/{instancekey} | Facets
*FeedApi* | [**feed**](docs/Api/FeedApi.md#feed) | **GET** /feed/{instancekey}/{profileKey} | Feed
*GuidedSellingApi* | [**guidedSellingCompare**](docs/Api/GuidedSellingApi.md#guidedsellingcompare) | **GET** /advisor/{instancekey} | Compare
*GuidedSellingApi* | [**guidedSellingFunnel**](docs/Api/GuidedSellingApi.md#guidedsellingfunnel) | **GET** /filterwizard/{instancekey} | Funnel
*InstanceApi* | [**instance**](docs/Api/InstanceApi.md#instance) | **GET** /instance/{instancekey} | Instance
*NavigationApi* | [**navigation**](docs/Api/NavigationApi.md#navigation) | **GET** /navigation/{instancekey} | Navigation
*NavigationApi* | [**navigationGrouped**](docs/Api/NavigationApi.md#navigationgrouped) | **GET** /navigation/grouped/{instancekey} | Grouped navigation
*NavigationSearchApi* | [**search**](docs/Api/NavigationSearchApi.md#search) | **GET** /navigation-search/{instancekey} | Search
*NavigationSearchApi* | [**searchGrouped**](docs/Api/NavigationSearchApi.md#searchgrouped) | **GET** /navigation-search/grouped/{instancekey} | Grouped search
*ProductsApi* | [**product**](docs/Api/ProductsApi.md#product) | **GET** /products/{instancekey}/{productNo} | Product
*ProductsApi* | [**products**](docs/Api/ProductsApi.md#products) | **GET** /products/{instancekey} | Products
*RecommendationsApi* | [**featuredRecommendations**](docs/Api/RecommendationsApi.md#featuredrecommendations) | **GET** /recommendations/featured/{instancekey}/{displayId} | Featured products
*RecommendationsApi* | [**productRecommendationsAll**](docs/Api/RecommendationsApi.md#productrecommendationsall) | **GET** /recommendations/product/{instancekey}/{productNo} | Product recommendations
*RecommendationsApi* | [**productRecommendationsSingle**](docs/Api/RecommendationsApi.md#productrecommendationssingle) | **GET** /recommendations/product/{instancekey}/{productRecId}/{productNo} | Product recommendations single rule
*RecommendationsApi* | [**productRecommendationsSingleGrouped**](docs/Api/RecommendationsApi.md#productrecommendationssinglegrouped) | **GET** /recommendations/grouped/{instancekey}/{productNo}/{groupKey} | Product recommendations multi rule
*SearchbannersApi* | [**searchbanners**](docs/Api/SearchbannersApi.md#searchbanners) | **GET** /searchbanners/{instancekey} | searchbanners
*StarterApi* | [**starter**](docs/Api/StarterApi.md#starter) | **GET** /starter/init/{instancekey} | Starter
*SuggestionsApi* | [**suggestions**](docs/Api/SuggestionsApi.md#suggestions) | **GET** /suggestions/{instancekey} | Suggestions
*SuggestionsApi* | [**suggestionsGrouped**](docs/Api/SuggestionsApi.md#suggestionsgrouped) | **GET** /suggestions/grouped/{instancekey} | Suggestions grouped
*SuggestionsApi* | [**suggestionsProducts**](docs/Api/SuggestionsApi.md#suggestionsproducts) | **GET** /suggestions/products/{instancekey} | Suggestion products
*SuggestionsApi* | [**suggestionsProductsGrouped**](docs/Api/SuggestionsApi.md#suggestionsproductsgrouped) | **GET** /suggestions/products/grouped/{instancekey} | Suggestion products grouped
*VisualSearchApi* | [**visualsearch**](docs/Api/VisualSearchApi.md#visualsearch) | **POST** /visual-search/{instancekey} | VisualSearch
*VisualSearchApi* | [**visualsearchGrouped**](docs/Api/VisualSearchApi.md#visualsearchgrouped) | **POST** /visual-search/grouped/{instancekey} | Grouped VisualSearch

## Models

- [Advisor](docs/Model/Advisor.md)
- [Answer](docs/Model/Answer.md)
- [Autocomplete](docs/Model/Autocomplete.md)
- [AutocompleteGroupItem](docs/Model/AutocompleteGroupItem.md)
- [AutocompleteGrouped](docs/Model/AutocompleteGrouped.md)
- [AutocompleteInstantSearch](docs/Model/AutocompleteInstantSearch.md)
- [AutocompleteItem](docs/Model/AutocompleteItem.md)
- [AutocompleteItemAttribute](docs/Model/AutocompleteItemAttribute.md)
- [AutocompleteItemGroup](docs/Model/AutocompleteItemGroup.md)
- [AutocompleteSuggestion](docs/Model/AutocompleteSuggestion.md)
- [Builder](docs/Model/Builder.md)
- [CatalogFilterTemplate](docs/Model/CatalogFilterTemplate.md)
- [CatalogGuidedSelling](docs/Model/CatalogGuidedSelling.md)
- [CatalogRecommendation](docs/Model/CatalogRecommendation.md)
- [CatalogRecommendationGroup](docs/Model/CatalogRecommendationGroup.md)
- [CatalogRecommendationsResponse](docs/Model/CatalogRecommendationsResponse.md)
- [CatalogSortTemplate](docs/Model/CatalogSortTemplate.md)
- [Category](docs/Model/Category.md)
- [CategoryTreeResponse](docs/Model/CategoryTreeResponse.md)
- [Clickpoint](docs/Model/Clickpoint.md)
- [FacetAttributesResponse](docs/Model/FacetAttributesResponse.md)
- [FacetsResponse](docs/Model/FacetsResponse.md)
- [FeaturedRecommendations](docs/Model/FeaturedRecommendations.md)
- [Feed](docs/Model/Feed.md)
- [FeedItem](docs/Model/FeedItem.md)
- [FeedItemAttribute](docs/Model/FeedItemAttribute.md)
- [FeedItemAttributeValue](docs/Model/FeedItemAttributeValue.md)
- [FilterWizard](docs/Model/FilterWizard.md)
- [FilterWizardAnswer](docs/Model/FilterWizardAnswer.md)
- [FilterWizardAttribute](docs/Model/FilterWizardAttribute.md)
- [FilterWizardAttributeValue](docs/Model/FilterWizardAttributeValue.md)
- [FilterWizardItem](docs/Model/FilterWizardItem.md)
- [FilterWizardQuestion](docs/Model/FilterWizardQuestion.md)
- [Instance](docs/Model/Instance.md)
- [InstanceFeature](docs/Model/InstanceFeature.md)
- [Language](docs/Model/Language.md)
- [Navigation](docs/Model/Navigation.md)
- [NavigationFacet](docs/Model/NavigationFacet.md)
- [NavigationFacetAttribute](docs/Model/NavigationFacetAttribute.md)
- [NavigationFacetBucket](docs/Model/NavigationFacetBucket.md)
- [NavigationFacetSettings](docs/Model/NavigationFacetSettings.md)
- [NavigationGroupItem](docs/Model/NavigationGroupItem.md)
- [NavigationGrouped](docs/Model/NavigationGrouped.md)
- [NavigationItem](docs/Model/NavigationItem.md)
- [NavigationItemAttribute](docs/Model/NavigationItemAttribute.md)
- [NavigationItemGroup](docs/Model/NavigationItemGroup.md)
- [NavigationItemOrigin](docs/Model/NavigationItemOrigin.md)
- [NavigationProperties](docs/Model/NavigationProperties.md)
- [NavigationSearchBanner](docs/Model/NavigationSearchBanner.md)
- [NavigationSortfield](docs/Model/NavigationSortfield.md)
- [ProductRecommendation](docs/Model/ProductRecommendation.md)
- [ProductRecommendationGrouped](docs/Model/ProductRecommendationGrouped.md)
- [ProductRecommendations](docs/Model/ProductRecommendations.md)
- [ProductRecommendationsGroup](docs/Model/ProductRecommendationsGroup.md)
- [ProductsResponse](docs/Model/ProductsResponse.md)
- [Question](docs/Model/Question.md)
- [Redirect](docs/Model/Redirect.md)
- [SearchBanner](docs/Model/SearchBanner.md)
- [StarterAnalyticsSettings](docs/Model/StarterAnalyticsSettings.md)
- [StarterComponent](docs/Model/StarterComponent.md)
- [StarterProductSettings](docs/Model/StarterProductSettings.md)
- [StarterResponse](docs/Model/StarterResponse.md)
- [StarterSettings](docs/Model/StarterSettings.md)
- [StarterUISettings](docs/Model/StarterUISettings.md)
- [Suggestion](docs/Model/Suggestion.md)
- [SuggestionGroup](docs/Model/SuggestionGroup.md)
- [SuggestionGroupedItem](docs/Model/SuggestionGroupedItem.md)
- [SuggestionItem](docs/Model/SuggestionItem.md)
- [SuggestionItemAttribute](docs/Model/SuggestionItemAttribute.md)
- [SuggestionItemOrigin](docs/Model/SuggestionItemOrigin.md)
- [Suggestions](docs/Model/Suggestions.md)
- [SuggestionsGroup](docs/Model/SuggestionsGroup.md)
- [SuggestionsGrouped](docs/Model/SuggestionsGrouped.md)
- [SuggestionsNavigationLink](docs/Model/SuggestionsNavigationLink.md)
- [SuggestionsNavigationLinkContext](docs/Model/SuggestionsNavigationLinkContext.md)
- [SuggestionsNavigationLinkContextCategory](docs/Model/SuggestionsNavigationLinkContextCategory.md)
- [SuggestionsNavigationLinkContextFacetFilter](docs/Model/SuggestionsNavigationLinkContextFacetFilter.md)
- [Visualproperties](docs/Model/Visualproperties.md)

## Authorization
All endpoints do not require authorization.
## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `0.6.0`
    - Package version: `1.0.0`
    - Generator version: `7.14.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
