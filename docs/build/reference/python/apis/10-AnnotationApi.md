---
title: Annotation API | Python SDK
---

# Annotation API

All URIs are relative to `http://localhost:1000`

Method | HTTP request | Description
------------- | ------------- | -------------
[**annotation_scores_increment**](AnnotationApi#annotation_scores_increment) | **POST** /annotation/\{annotation\}/scores/increment | '/annotation/\{annotation\}/scores/increment' [POST]
[**annotation_specific_annotation_snapshot**](AnnotationApi#annotation_specific_annotation_snapshot) | **GET** /annotation/\{annotation\} | /annotation/\{annotation\} [GET]
[**annotation_update**](AnnotationApi#annotation_update) | **POST** /annotation/update | /annotation/update [POST]


## **annotation_scores_increment** {#annotation_scores_increment}
> annotation_scores_increment(annotation, seeded_score_increment=seeded_score_increment)

'/annotation/\{annotation\}/scores/increment' [POST]

This will take in a SeededScoreIncrement and will increment the material relative to the incoming body.

### Example {#annotation_scores_increment-example}


```python
import pieces_os_client
from pieces_os_client.models.seeded_score_increment import SeededScoreIncrement
from pieces_os_client.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost:1000
# See configuration.py for a list of all supported configuration parameters.
configuration = pieces_os_client.Configuration(
    host="http://localhost:1000"
)


# Enter a context with an instance of the API client
with pieces_os_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = pieces_os_client.AnnotationApi(api_client)
    annotation = 'annotation_example' # str | This is a specific annotation uuid.
    seeded_score_increment = pieces_os_client.SeededScoreIncrement() # SeededScoreIncrement |  (optional)

    try:
        # '/annotation/\{annotation\}/scores/increment' [POST]
        api_instance.annotation_scores_increment(annotation, seeded_score_increment=seeded_score_increment)
    except Exception as e:
        print("Exception when calling AnnotationApi->annotation_scores_increment: %s\n" % e)
```



### Parameters {#annotation_scores_increment-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **annotation** | **str**| This is a specific annotation uuid. | 
 **seeded_score_increment** | [**SeededScoreIncrement**](../models/SeededScoreIncrement)|  | [optional] 

### Return type {#annotation_scores_increment-return-type}

void (empty response body)

### Authorization {#annotation_scores_increment-authorization}

No authorization required

### HTTP request headers {#annotation_scores_increment-http-request-headers}

 - **Content-Type**: application/json
 - **Accept**: text/plain


### HTTP response details {#annotation_scores_increment-http-response-details}

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | No Content |  -  |
**500** | Internal Server Error |  -  |

## **annotation_specific_annotation_snapshot** {#annotation_specific_annotation_snapshot}
> Annotation annotation_specific_annotation_snapshot(annotation)

/annotation/\{annotation\} [GET]

This will get a snapshot of a specific annotation.

### Example {#annotation_specific_annotation_snapshot-example}


```python
import pieces_os_client
from pieces_os_client.models.annotation import Annotation
from pieces_os_client.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost:1000
# See configuration.py for a list of all supported configuration parameters.
configuration = pieces_os_client.Configuration(
    host="http://localhost:1000"
)


# Enter a context with an instance of the API client
with pieces_os_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = pieces_os_client.AnnotationApi(api_client)
    annotation = 'annotation_example' # str | This is a specific annotation uuid.

    try:
        # /annotation/\{annotation\} [GET]
        api_response = api_instance.annotation_specific_annotation_snapshot(annotation)
        print("The response of AnnotationApi->annotation_specific_annotation_snapshot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AnnotationApi->annotation_specific_annotation_snapshot: %s\n" % e)
```



### Parameters {#annotation_specific_annotation_snapshot-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **annotation** | **str**| This is a specific annotation uuid. | 

### Return type {#annotation_specific_annotation_snapshot-return-type}

[**Annotation**](../models/Annotation)

### Authorization {#annotation_specific_annotation_snapshot-authorization}

No authorization required

### HTTP request headers {#annotation_specific_annotation_snapshot-http-request-headers}

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain


### HTTP response details {#annotation_specific_annotation_snapshot-http-response-details}

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**500** | Internal Server Error |  -  |

## **annotation_update** {#annotation_update}
> Annotation annotation_update(annotation=annotation)

/annotation/update [POST]

This will update a specific annotation.

### Example {#annotation_update-example}


```python
import pieces_os_client
from pieces_os_client.models.annotation import Annotation
from pieces_os_client.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost:1000
# See configuration.py for a list of all supported configuration parameters.
configuration = pieces_os_client.Configuration(
    host="http://localhost:1000"
)


# Enter a context with an instance of the API client
with pieces_os_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = pieces_os_client.AnnotationApi(api_client)
    annotation = pieces_os_client.Annotation() # Annotation |  (optional)

    try:
        # /annotation/update [POST]
        api_response = api_instance.annotation_update(annotation=annotation)
        print("The response of AnnotationApi->annotation_update:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AnnotationApi->annotation_update: %s\n" % e)
```



### Parameters {#annotation_update-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **annotation** | [**Annotation**](../models/Annotation)|  | [optional] 

### Return type {#annotation_update-return-type}

[**Annotation**](../models/Annotation)

### Authorization {#annotation_update-authorization}

No authorization required

### HTTP request headers {#annotation_update-http-request-headers}

 - **Content-Type**: application/json
 - **Accept**: application/json, text/plain


### HTTP response details {#annotation_update-http-response-details}

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**500** | Internal Server Error |  -  |

