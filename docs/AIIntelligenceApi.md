# whisper_api_sdk.AIIntelligenceApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**ai_attribute**](AIIntelligenceApi.md#ai_attribute) | **POST** /v1/ops/ai/attribute | Threat Actor Attribution (Asynchronous)
[**ai_correlate**](AIIntelligenceApi.md#ai_correlate) | **POST** /v1/ops/ai/correlate | Global Indicator Correlation (Asynchronous)
[**ai_investigate**](AIIntelligenceApi.md#ai_investigate) | **POST** /v1/ops/ai/investigate | AI Threat Investigation (Asynchronous)
[**ai_pivot**](AIIntelligenceApi.md#ai_pivot) | **POST** /v1/ops/ai/pivot | AI Infrastructure Pivot (Asynchronous)
[**find_similar_cases**](AIIntelligenceApi.md#find_similar_cases) | **POST** /v1/ops/ai/similar-cases | Find Similar Cases (Asynchronous)
[**get_industry_benchmark**](AIIntelligenceApi.md#get_industry_benchmark) | **GET** /v1/ops/ai/benchmark/{industry} | Get Industry Security Benchmark (Synchronous)


# **ai_attribute**
> AttributeResult ai_attribute(attribute_request)

Threat Actor Attribution (Asynchronous)

<p>Analyzes indicators and context to identify potential threat actors and campaigns. Uses ML clustering and TTP matching against known threat actor profiles.</p>
<h4>Attribution Analysis:</h4>
<ul>
    <li><b>Actor Identification:</b> Potential threat actor matches with confidence</li>
    <li><b>Campaign Clustering:</b> Groups indicators into potential campaigns</li>
    <li><b>TTP Mapping:</b> MITRE ATT&CK technique mapping</li>
    <li><b>Historical Context:</b> Known actor activity patterns</li>
</ul>
<h4>Limitations:</h4>
<p>Maximum 500 indicators per request. Attribution is probabilistic and should be validated.</p>
<h4>Performance:</h4>
<p>Campaign clustering and analysis. Expected: 60-300 seconds.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.attribute_request import AttributeRequest
from whisper_api_sdk.models.attribute_result import AttributeResult
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.AIIntelligenceApi(api_client)
    attribute_request = whisper_api_sdk.AttributeRequest() # AttributeRequest | Attribution request

    try:
        # Threat Actor Attribution (Asynchronous)
        api_response = api_instance.ai_attribute(attribute_request)
        print("The response of AIIntelligenceApi->ai_attribute:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AIIntelligenceApi->ai_attribute: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **attribute_request** | [**AttributeRequest**](AttributeRequest.md)| Attribution request | 

### Return type

[**AttributeResult**](AttributeResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Attribution analysis job accepted. Poll GET /v1/ops/jobs/{jobId} for results. |  -  |
**200** | Job result schema (returned via GET /v1/ops/jobs/{jobId} when job completes) |  -  |
**400** | Invalid request or exceeds 500 indicator limit. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **ai_correlate**
> CorrelateResult ai_correlate(correlate_request)

Global Indicator Correlation (Asynchronous)

<p>Correlates your indicators against anonymized global threat data from all customers. Identifies shared campaigns, widespread threats, and prevalence across industries.</p>
<h4>Correlation Analysis:</h4>
<ul>
    <li><b>Prevalence:</b> How common are these indicators across our customer base</li>
    <li><b>Industry Breakdown:</b> Which industries are seeing these indicators</li>
    <li><b>Campaign Detection:</b> Are these part of a broader campaign</li>
    <li><b>First/Last Seen:</b> Global timeline of indicator activity</li>
    <li><b>Co-occurrence:</b> Indicators frequently seen together</li>
</ul>
<h4>Limitations:</h4>
<p>Maximum 100 indicators per request.</p>
<h4>Performance:</h4>
<p>Cross-customer correlation. Expected: 10-60 seconds.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.correlate_request import CorrelateRequest
from whisper_api_sdk.models.correlate_result import CorrelateResult
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.AIIntelligenceApi(api_client)
    correlate_request = whisper_api_sdk.CorrelateRequest() # CorrelateRequest | Correlation request

    try:
        # Global Indicator Correlation (Asynchronous)
        api_response = api_instance.ai_correlate(correlate_request)
        print("The response of AIIntelligenceApi->ai_correlate:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AIIntelligenceApi->ai_correlate: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **correlate_request** | [**CorrelateRequest**](CorrelateRequest.md)| Correlation request | 

### Return type

[**CorrelateResult**](CorrelateResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Correlation job accepted. Poll GET /v1/ops/jobs/{jobId} for results. |  -  |
**200** | Job result schema (returned via GET /v1/ops/jobs/{jobId} when job completes) |  -  |
**400** | Invalid request or exceeds 100 indicator limit. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **ai_investigate**
> InvestigateResult ai_investigate(investigate_request)

AI Threat Investigation (Asynchronous)

<p>Initiates a comprehensive AI-powered threat investigation for an indicator. Uses large language models to analyze threat intelligence, generate insights, and provide actionable recommendations.</p>
<h4>Investigation Output:</h4>
<ul>
    <li><b>Verdict:</b> Threat assessment with confidence score</li>
    <li><b>Timeline:</b> Activity timeline reconstruction</li>
    <li><b>Analysis:</b> Detailed findings from multiple data sources</li>
    <li><b>Related Indicators:</b> Discovered related infrastructure</li>
    <li><b>Recommendations:</b> Suggested response actions</li>
</ul>
<h4>Performance:</h4>
<p>LLM-based analysis. Expected completion: 30-180 seconds depending on complexity.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.investigate_request import InvestigateRequest
from whisper_api_sdk.models.investigate_result import InvestigateResult
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.AIIntelligenceApi(api_client)
    investigate_request = {"indicator":"8.8.8.8","indicatorType":"ip","depth":"standard","context":{"hypothesis":"Suspicious outbound connection detected"}} # InvestigateRequest | Investigation request. Required fields: - **indicator**: The IP, domain, or hash to investigate - **indicatorType**: Must be \"ip\", \"domain\", or \"hash\"  Optional fields: - **depth**: Investigation depth (\"quick\", \"standard\", \"comprehensive\"). Default: \"standard\" - **context**: Object with optional fields: hypothesis (string), relatedIndicators (array), timeRange (string) 

    try:
        # AI Threat Investigation (Asynchronous)
        api_response = api_instance.ai_investigate(investigate_request)
        print("The response of AIIntelligenceApi->ai_investigate:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AIIntelligenceApi->ai_investigate: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **investigate_request** | [**InvestigateRequest**](InvestigateRequest.md)| Investigation request. Required fields: - **indicator**: The IP, domain, or hash to investigate - **indicatorType**: Must be \&quot;ip\&quot;, \&quot;domain\&quot;, or \&quot;hash\&quot;  Optional fields: - **depth**: Investigation depth (\&quot;quick\&quot;, \&quot;standard\&quot;, \&quot;comprehensive\&quot;). Default: \&quot;standard\&quot; - **context**: Object with optional fields: hypothesis (string), relatedIndicators (array), timeRange (string)  | 

### Return type

[**InvestigateResult**](InvestigateResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Investigation job accepted. Poll GET /v1/ops/jobs/{jobId} for results. |  -  |
**200** | Job result schema (returned via GET /v1/ops/jobs/{jobId} when job completes) |  -  |
**400** | Invalid request. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **ai_pivot**
> PivotResult ai_pivot(pivot_request)

AI Infrastructure Pivot (Asynchronous)

<p>Performs intelligent infrastructure pivoting starting from an indicator. Uses ML to identify the most relevant relationships and suggest investigation paths.</p>
<h4>Pivot Strategies:</h4>
<ul>
    <li><b>infrastructure:</b> Shared hosting, nameservers, certificates</li>
    <li><b>registration:</b> Same registrant, registration patterns</li>
    <li><b>behavioral:</b> Similar traffic patterns, communication</li>
    <li><b>temporal:</b> Co-occurrence within time windows</li>
</ul>
<h4>Response Includes:</h4>
<ul>
    <li>Discovered related indicators with relevance scores</li>
    <li>Suggested investigation paths ranked by priority</li>
    <li>Relationship graph data</li>
</ul>
<h4>Performance:</h4>
<p>Graph traversal with ML ranking. Expected: 10-120 seconds based on depth.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.pivot_request import PivotRequest
from whisper_api_sdk.models.pivot_result import PivotResult
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.AIIntelligenceApi(api_client)
    pivot_request = whisper_api_sdk.PivotRequest() # PivotRequest | Pivot request

    try:
        # AI Infrastructure Pivot (Asynchronous)
        api_response = api_instance.ai_pivot(pivot_request)
        print("The response of AIIntelligenceApi->ai_pivot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AIIntelligenceApi->ai_pivot: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pivot_request** | [**PivotRequest**](PivotRequest.md)| Pivot request | 

### Return type

[**PivotResult**](PivotResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Pivot analysis job accepted. Poll GET /v1/ops/jobs/{jobId} for results. |  -  |
**200** | Job result schema (returned via GET /v1/ops/jobs/{jobId} when job completes) |  -  |
**400** | Invalid request. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_similar_cases**
> SimilarCasesResult find_similar_cases(similar_cases_request)

Find Similar Cases (Asynchronous)

<p>Uses ML to find historical threat cases similar to the current investigation. Helps analysts understand attack patterns and expected outcomes.</p>
<h4>Matching Criteria:</h4>
<ul>
    <li>Indicator overlap and relationships</li>
    <li>Behavioral patterns and TTPs</li>
    <li>Infrastructure characteristics</li>
    <li>Attack progression similarities</li>
</ul>
<h4>Response Includes:</h4>
<ul>
    <li>Similar cases with similarity scores</li>
    <li>Case outcomes and verdicts</li>
    <li>Common patterns across matches</li>
</ul>
<h4>Performance:</h4>
<p>ML similarity matching. Expected completion: 5-30 seconds.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.similar_cases_request import SimilarCasesRequest
from whisper_api_sdk.models.similar_cases_result import SimilarCasesResult
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.AIIntelligenceApi(api_client)
    similar_cases_request = whisper_api_sdk.SimilarCasesRequest() # SimilarCasesRequest | Similar cases request

    try:
        # Find Similar Cases (Asynchronous)
        api_response = api_instance.find_similar_cases(similar_cases_request)
        print("The response of AIIntelligenceApi->find_similar_cases:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AIIntelligenceApi->find_similar_cases: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **similar_cases_request** | [**SimilarCasesRequest**](SimilarCasesRequest.md)| Similar cases request | 

### Return type

[**SimilarCasesResult**](SimilarCasesResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Similar cases search job accepted. Poll GET /v1/ops/jobs/{jobId} for results. |  -  |
**200** | Job result schema (returned via GET /v1/ops/jobs/{jobId} when job completes) |  -  |
**400** | Invalid request. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_industry_benchmark**
> BenchmarkResponse get_industry_benchmark(industry, size=size, region=region)

Get Industry Security Benchmark (Synchronous)

<p>Returns anonymized, aggregated security metrics for your industry vertical. Compare your security posture against peers.</p>
<h4>Available Industries:</h4>
<ul>
    <li>financial_services, healthcare, technology, retail, manufacturing</li>
    <li>energy, telecommunications, government, education, media</li>
</ul>
<h4>Metrics Included:</h4>
<ul>
    <li><b>Risk Scores:</b> Average risk score, percentiles (25th, 50th, 75th, 90th)</li>
    <li><b>Response Metrics:</b> Mean time to detect (MTTD), mean time to respond (MTTR)</li>
    <li><b>Detection Metrics:</b> Detection rate, false positive rate</li>
    <li><b>Threat Profile:</b> Top threats, common attack vectors, targeted assets</li>
    <li><b>Trends:</b> 30-day risk trend direction and change percentage</li>
</ul>
<h4>Performance:</h4>
<p>Pre-aggregated data. Response time typically under 500ms with 1-hour cache.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.benchmark_response import BenchmarkResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.AIIntelligenceApi(api_client)
    industry = 'financial_services' # str | Industry vertical code
    size = 'enterprise' # str | Organization size filter. Compares against organizations of similar size. (optional)
    region = 'north_america' # str | Geographic region filter. Compares against organizations in the same region. (optional)

    try:
        # Get Industry Security Benchmark (Synchronous)
        api_response = api_instance.get_industry_benchmark(industry, size=size, region=region)
        print("The response of AIIntelligenceApi->get_industry_benchmark:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AIIntelligenceApi->get_industry_benchmark: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **industry** | **str**| Industry vertical code | 
 **size** | **str**| Organization size filter. Compares against organizations of similar size. | [optional] 
 **region** | **str**| Geographic region filter. Compares against organizations in the same region. | [optional] 

### Return type

[**BenchmarkResponse**](BenchmarkResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successfully retrieved industry benchmark. |  -  |
**400** | Invalid industry code. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

