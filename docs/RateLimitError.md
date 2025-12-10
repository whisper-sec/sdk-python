# RateLimitError

Rate limit exceeded error response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**error** | **str** | Error type | 
**message** | **str** | Human-readable error message with rate limit category | 
**retry_after** | **int** | Number of seconds to wait before retrying | 

## Example

```python
from whisper_api_sdk.models.rate_limit_error import RateLimitError

# TODO update the JSON string below
json = "{}"
# create an instance of RateLimitError from a JSON string
rate_limit_error_instance = RateLimitError.from_json(json)
# print the JSON string representation of the object
print(RateLimitError.to_json())

# convert the object into a dict
rate_limit_error_dict = rate_limit_error_instance.to_dict()
# create an instance of RateLimitError from a dict
rate_limit_error_from_dict = RateLimitError.from_dict(rate_limit_error_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


