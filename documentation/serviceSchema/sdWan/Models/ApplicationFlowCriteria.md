# ApplicationFlowCriteria
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ethertype** | [**List**](integer.md) | Ethertype. Integer in the range 0x600 to 0xffff. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**cVlans** | [**List**](integer.md) | C-VLAN ID List. Integer in range 0 to 4096. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**ipv4SourceAddress** | [**List**](Ipv4Prefix.md) | IPv4 Source Address. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**ipv4DestinationAddress** | [**List**](Ipv4Prefix.md) | IPv4 Destination Address. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**ipv4SourceOrDestinationAddress** | [**List**](Ipv4Prefix.md) | IPv4 Source or Destination Address. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**ipv4ProtocolList** | [**List**](integer.md) | IPv4 Destination Address. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**ipv6SourceAddress** | [**List**](Ipv6Prefix.md) | IPv6 Source Address. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**ipv6DestinationAddress** | [**List**](Ipv6Prefix.md) | IPv6 Destination Address. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**ipv6SourceOrDestinationAddress** | [**List**](Ipv6Prefix.md) | IPv6 Source or Destination Address. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**nextHeadV6** | [**List**](integer.md) | IPv6 Next Header List. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**tcpUdpSourcePortList** | [**List**](integer.md) | TCP/UDP Source Port List. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**tcpUdpDestinationPortList** | [**List**](integer.md) | TCP/UDP Destination Port List. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**tcpUdpSourceOrDestinationPortList** | [**List**](integer.md) | TCP/UDP Source or Destination Port List. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**any** | [**Boolean**](boolean.md) | Match Any IP Packet. Reference MEF 70 Section 8.7 Table-4 Required Application Flow Criteria. | [optional] [default to null]
**applicationIdentifier** | [**List**](ApplicationIdentifier.md) |  | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

