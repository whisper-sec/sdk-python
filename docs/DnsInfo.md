# DnsInfo

DNS records and resolution data for the domain

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**arecords** | **List[str]** |  | [optional] 
**a_records** | **List[str]** | A records (IPv4 addresses) | [optional] 
**aaaa_records** | **List[str]** | AAAA records (IPv6 addresses) | [optional] 
**mx_records** | **List[object]** | MX records (mail servers) with priority and hostname | [optional] 
**ns_records** | **List[str]** | NS records (name servers) | [optional] 
**txt_records** | **List[str]** | TXT records (text records for SPF, DKIM, etc.) | [optional] 
**cname_records** | **List[str]** | CNAME records (canonical name aliases) | [optional] 

## Example

```python
from whisper_api_sdk.models.dns_info import DnsInfo

# TODO update the JSON string below
json = "{}"
# create an instance of DnsInfo from a JSON string
dns_info_instance = DnsInfo.from_json(json)
# print the JSON string representation of the object
print(DnsInfo.to_json())

# convert the object into a dict
dns_info_dict = dns_info_instance.to_dict()
# create an instance of DnsInfo from a dict
dns_info_from_dict = DnsInfo.from_dict(dns_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


