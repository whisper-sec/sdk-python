# JobResponse

Response returned when an asynchronous job is created. Contains the job ID and status URL for polling.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**job_id** | **str** | Unique identifier for the job. Use this ID to poll for job status and results. | 
**status** | **str** | Current status of the job | 
**status_url** | **str** | URL endpoint to poll for job status and results. Typically &#x60;/v1/ops/jobs/{jobId}&#x60;. | 
**message** | **str** | Human-readable message describing the job acceptance or current state | [optional] 

## Example

```python
from whisper_api_sdk.models.job_response import JobResponse

# TODO update the JSON string below
json = "{}"
# create an instance of JobResponse from a JSON string
job_response_instance = JobResponse.from_json(json)
# print the JSON string representation of the object
print(JobResponse.to_json())

# convert the object into a dict
job_response_dict = job_response_instance.to_dict()
# create an instance of JobResponse from a dict
job_response_from_dict = JobResponse.from_dict(job_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


