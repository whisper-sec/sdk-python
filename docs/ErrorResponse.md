# ErrorResponse

Standard error response returned when an API request fails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **int** | The HTTP status code of the error | 
**error** | **str** | A short, machine-readable error code | 
**message** | **str** | A human-readable error message providing more detail | 
**details** | **object** | Additional details about the error, including field-specific validation errors | [optional] 
**timestamp** | **datetime** | The timestamp when the error occurred | 
**trace_id** | **str** | A unique trace ID for this request, useful for debugging | [optional] 
**path** | **str** | The API path that generated this error | [optional] 

## Example

```python
from whisper_api_sdk.models.error_response import ErrorResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ErrorResponse from a JSON string
error_response_instance = ErrorResponse.from_json(json)
# print the JSON string representation of the object
print(ErrorResponse.to_json())

# convert the object into a dict
error_response_dict = error_response_instance.to_dict()
# create an instance of ErrorResponse from a dict
error_response_from_dict = ErrorResponse.from_dict(error_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


