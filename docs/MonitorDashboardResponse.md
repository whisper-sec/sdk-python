# MonitorDashboardResponse

Monitoring dashboard summary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_checks** | **int** | Total number of checks | [optional] 
**passing_checks** | **int** | Number of passing checks | [optional] 
**failing_checks** | **int** | Number of failing checks | [optional] 
**degraded_checks** | **int** | Number of degraded checks | [optional] 
**overall_status** | **str** | Overall status | [optional] 
**avg_uptime24_hours** | **float** | Average uptime percentage over the last 24 hours | [optional] 
**avg_uptime7_days** | **float** | Average uptime percentage over the last 7 days | [optional] 
**avg_uptime30_days** | **float** | Average uptime percentage over the last 30 days | [optional] 
**avg_response_time** | **int** | Average response time across all checks in milliseconds | [optional] 
**checks_by_type** | **Dict[str, int]** | Count of checks by type | [optional] 
**checks_by_status** | **Dict[str, int]** | Count of checks by status | [optional] 
**last_updated** | **datetime** | When this dashboard data was last updated | [optional] 

## Example

```python
from whisper_api_sdk.models.monitor_dashboard_response import MonitorDashboardResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MonitorDashboardResponse from a JSON string
monitor_dashboard_response_instance = MonitorDashboardResponse.from_json(json)
# print the JSON string representation of the object
print(MonitorDashboardResponse.to_json())

# convert the object into a dict
monitor_dashboard_response_dict = monitor_dashboard_response_instance.to_dict()
# create an instance of MonitorDashboardResponse from a dict
monitor_dashboard_response_from_dict = MonitorDashboardResponse.from_dict(monitor_dashboard_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


