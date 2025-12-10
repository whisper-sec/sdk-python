# JobSummary

Summary of a job

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**job_id** | **str** | Unique job identifier | [optional] 
**type** | **str** | Type of job | [optional] 
**status** | **str** | Current job status | [optional] 
**created_at** | **str** | Job creation timestamp | [optional] 
**completed_at** | **str** | Job completion timestamp (if completed) | [optional] 
**progress** | [**ProgressInfo**](ProgressInfo.md) | Job progress information | [optional] 
**error** | [**ErrorInfo**](ErrorInfo.md) | Error information (if failed) | [optional] 

## Example

```python
from whisper_api_sdk.models.job_summary import JobSummary

# TODO update the JSON string below
json = "{}"
# create an instance of JobSummary from a JSON string
job_summary_instance = JobSummary.from_json(json)
# print the JSON string representation of the object
print(JobSummary.to_json())

# convert the object into a dict
job_summary_dict = job_summary_instance.to_dict()
# create an instance of JobSummary from a dict
job_summary_from_dict = JobSummary.from_dict(job_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


