# IspInfo

Internet Service Provider and Autonomous System information

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | ISP name | [optional] 
**organization** | **str** | Organization that owns/operates this IP range | [optional] 
**asn** | **int** | Autonomous System Number | [optional] 
**asn_organization** | **str** | Organization name associated with the ASN | [optional] 

## Example

```python
from whisper_api_sdk.models.isp_info import IspInfo

# TODO update the JSON string below
json = "{}"
# create an instance of IspInfo from a JSON string
isp_info_instance = IspInfo.from_json(json)
# print the JSON string representation of the object
print(IspInfo.to_json())

# convert the object into a dict
isp_info_dict = isp_info_instance.to_dict()
# create an instance of IspInfo from a dict
isp_info_from_dict = IspInfo.from_dict(isp_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


