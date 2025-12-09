# GenericSuccessResponse

Generic success response for operations that don't return specific data

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **str** | Status of the operation | [optional] 
**message** | **str** | Human-readable message describing the operation result | [optional] 
**id** | **str** | ID of the related resource (if applicable) | [optional] 
**deleted** | **bool** | Whether the operation was successful (for delete operations) | [optional] 
**cleared** | **bool** | Whether the operation was successful (for clear operations) | [optional] 
**schedule_id** | **str** | Schedule ID (for schedule-related operations) | [optional] 

## Example

```python
from whisper_api_sdk.models.generic_success_response import GenericSuccessResponse

# TODO update the JSON string below
json = "{}"
# create an instance of GenericSuccessResponse from a JSON string
generic_success_response_instance = GenericSuccessResponse.from_json(json)
# print the JSON string representation of the object
print(GenericSuccessResponse.to_json())

# convert the object into a dict
generic_success_response_dict = generic_success_response_instance.to_dict()
# create an instance of GenericSuccessResponse from a dict
generic_success_response_from_dict = GenericSuccessResponse.from_dict(generic_success_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


