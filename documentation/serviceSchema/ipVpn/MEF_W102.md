<center>
<img src="media/MEF_Logo.png" alt="MEF_Logo" width="469" height="281" />
</center>

<p style="text-align:center; font-family:verdana; font-size:300%"> <strong>Working Draft <br /> MEF W102 v0.1</strong> </p>
<br />
<p style="text-align:center; font-family:verdana; font-size:300%"> <strong>LSO Legato Service Provisioning Specification-
<br />IP Services</strong> </p>
<p style="text-align:center; font-family:verdana; font-size:250%"> <strong>April 2021</strong> </p>
<br />
<p style="text-align:center; font-family:verdana; font-size:175%; color:red"> <strong>This draft represents MEF work in progress and is subject to change.</strong> </p>

<p style="page-break-before:always;"></p>

Disclaimer
© MEF Forum 2021. All Rights Reserved.

The information in this publication is freely available for reproduction and use by any recipient and is believed to be accurate as of its publication date. Such information is subject to change without notice and MEF Forum (MEF) is not responsible for any errors. MEF does not assume responsibility to update or correct any information in this publication. No representation or warranty, expressed or implied, is made by MEF concerning the completeness, accuracy, or applicability of any information contained herein and no liability of any kind shall be assumed by MEF as a result of reliance upon such information.
The information contained herein is intended to be used without modification by the recipient or user of this document. MEF is not responsible or liable for any modifications to this document made by any other party.

The receipt or any use of this document or its contents does not in any way create, by implication or otherwise:

1. any express or implied license or right to or under any patent, copyright, trademark or trade secret rights held or claimed by any MEF member which are or may be associated with the ideas, techniques, concepts or expressions contained herein; nor
2. any warranty or representation that any MEF members will announce any product(s) and/or service(s) related thereto, or if such announcements are made, that such announced product(s) and/or service(s) embody any or all of the ideas, technologies, or concepts contained herein; nor
3. any form of relationship between any MEF member and the recipient or user of this document.

Implementation or use of specific MEF standards, specifications, or recommendations will be voluntary. This document is provided “as is” with no warranties whatsoever, express of implied, including without limitation, any warranties of merchantability, non-infringement, accuracy, completeness or fitness for any particular purpose. MEF and its members disclaim all liability, including liability for infringement of any proprietary rights, relating to use of information in this document.

<p style="page-break-before:always;"></p>
<p style="text-align:center; font-family:verdana; font-size:200%"> <strong>Table of Contents</strong> </p>

<!---Table Of Contents Here--->
- [1. List of Contributing Members](#1-list-of-contributing-members)
- [2. Abstract and Introduction](#2-abstract-and-introduction)
- [3. Terminology and Abbreviations](#3-terminology-and-abbreviations)
- [4. Overview of LSO-Legato](#4-overview-of-lso-legato)
- [5. Superclasses and Resources in support of Subscriber and Operator Carrier Ethernet Services](#5-superclasses-and-resources-in-support-of-subscriber-and-operator-carrier-ethernet-services)
- [6. Overview of Subscriber Ethernet Services](#6-overview-of-subscriber-ethernet-services)
- [7. Overview of Operator Ethernet Services](#7-overview-of-operator-ethernet-services)
- [8. Data Model Design Principles](#8-data-model-design-principles)
- [9. Data Models for Carrier Ethernet Subscriber and Operator Services](#9-data-models-for-carrier-ethernet-subscriber-and-operator-services)
  - [9.1 Service Order and Carrier Ethernet Associations](#91-service-order-and-carrier-ethernet-associations)
  - [9.2. Organization and Structure of the JSON Schemas](#92-organization-and-structure-of-the-json-schemas)
    - [9.2.1 CarrierEthernetSubscriberUni-CarrierEthernetEvcEndPoint Relationship](#921-carrierethernetsubscriberuni-carrierethernetevcendpoint-relationship)
    - [9.2.2 CarrierEthernetEvc-CarrierEthernetEvcEndPoint Relationship](#922-carrierethernetevc-carrierethernetevcendpoint-relationship)
- [10. Carrier Ethernet Superclass and Attributes](#10-carrier-ethernet-superclass-and-attributes)
  - [10.1 CarrierEthernetExternalInterface Service Attributes](#101-carrierethernetexternalinterface-service-attributes)
  - [10.2 CarrierEthernetServiceEndPoint Service Attributes](#102-carrierethernetserviceendpoint-service-attributes)
  - [10.3 CarrierEthernetService Service Attributes](#103-carrierethernetservice-service-attributes)
  - [10.4 CarrierEthernetUni Service Attributes](#104-carrierethernetuni-service-attributes)
- [11. Subscriber Ethernet Services](#11-subscriber-ethernet-services)
  - [11.1 CarrierEthernetSubscriberUni Service Attributes](#111-carrierethernetsubscriberuni-service-attributes)
  - [11.2 CarrierEthernetSubscriberUniRef Service Attributes](#112-carrierethernetsubscriberuniref-service-attributes)
  - [11.3 CarrierEthernetEvcEndPoint Service Attributes](#113-carrierethernetevcendpoint-service-attributes)
  - [11.4 CarrierEthernetEvcEndPointRef Attributes](#114-carrierethernetevcendpointref-attributes)
  - [11.5 CarrierEthernetEvc Service Attributes](#115-carrierethernetevc-service-attributes)
  - [11.6 CarrierEthernetEvcRef Attributes](#116-carrierethernetevcref-attributes)
- [12. Operator Ethernet Services](#12-operator-ethernet-services)
  - [12.1 CarrierEthernetOperatorUni Service Attributes](#121-carrierethernetoperatoruni-service-attributes)
  - [12.2 CarrierEthernetVirtualUni Service Attributes](#122-carrierethernetvirtualuni-service-attributes)
  - [12.3 CarrierEthernetVirtualUniRef Attributes](#123-carrierethernetvirtualuniref-attributes)
  - [12.4 CarrierEthernetEnni Service Attributes](#124-carrierethernetenni-service-attributes)
  - [12.5 CarrierEthernetEnniService Service Attributes](#125-carrierethernetenniservice-service-attributes)
  - [12.6 CarrierEthernetOvcEndPoint Service Attributes](#126-carrierethernetovcendpoint-service-attributes)
  - [12.7 CarrierEthernetOvcEndPointRef Attributes](#127-carrierethernetovcendpointref-attributes)
  - [12.8 CarrierEthernetOvc Service Attributes](#128-carrierethernetovc-service-attributes)
  - [12.9 CarrierEthernetOvcRef Attributes](#129-carrierethernetovcref-attributes)
- [13. Common Resources](#13-common-resources)
  - [13.1 AdminState](#131-adminstate)
  - [13.2 AggLinkDepth](#132-agglinkdepth)
  - [13.3 AvailableMegLevel](#133-availablemeglevel)
  - [13.4 BwpFlow](#134-bwpflow)
  - [13.5 ConnectionType](#135-connectiontype)
  - [13.6 ConversationIdToAggregationLinkMap](#136-conversationidtoaggregationlinkmap)
  - [13.7 ColorFieldType](#137-colorfieldtype)
  - [13.8 ColorIdentifier](#138-coloridentifier)
  - [13.9 ColorMode](#139-colormode)
  - [13.10 CosIdentifier](#1310-cosidentifier)
  - [13.11 CosNameAndColorToDeiPac](#1311-cosnameandcolortodeipac)
  - [13.12 CosNameAndColorToPcpPac](#1312-cosnameandcolortopcppac)
  - [13.13 CosNameToPcpPac](#1313-cosnametopcppac)
  - [13.14 DeiColorIdPac](#1314-deicoloridpac)
  - [13.15 DeiOrDiscard](#1315-deiordiscard)
  - [13.16 DscpColorIdPac](#1316-dscpcoloridpac)
  - [13.17 DscpEecIdPac](#1317-dscpeecidpac)
  - [13.18 EecIdentifier](#1318-eecidentifier)
  - [13.19 Envelope](#1319-envelope)
  - [13.20 EthernetFrameFormat](#1320-ethernetframeformat)
  - [13.21 EvcEpEgressMap](#1321-evcepegressmap)
  - [13.22 EvcEpEgressMapType](#1322-evcepegressmaptype)
  - [13.23 EvcEndPointRole](#1323-evcendpointrole)
  - [13.24 FrameColor](#1324-framecolor)
  - [13.25 FrameDelivery](#1325-framedelivery)
  - [13.26 Identifier45](#1326-identifier45)
  - [13.27 IpVersion](#1327-ipversion)
  - [13.28 L2cpAddressSet](#1328-l2cpaddressset)
  - [13.29 L2cpPeering](#1329-l2cppeering)
  - [13.30 L2cpProtocol](#1330-l2cpprotocol)
  - [13.31 L2cpProtocolType](#1331-l2cpprotocoltype)
  - [13.32 MepDirection](#1332-mepdirection)
  - [13.33 MepLevelAndDirection](#1333-meplevelanddirection)
  - [13.34 OperationalState](#1334-operationalstate)
  - [13.35 OvcEndPointRole](#1335-ovcendpointrole)
  - [13.36 OvcEpEgressMap](#1336-ovcepegressmap)
  - [13.37 OvcEpEgressMapType](#1337-ovcepegressmaptype)
  - [13.38 PcpColorIdPac](#1338-pcpcoloridpac)
  - [13.39 PcpEecIdPac](#1339-pcpeecidpac)
  - [13.40 PcpOrDiscard](#1340-pcpordiscard)
  - [13.41 PhysicalLayer](#1341-physicallayer)
  - [13.42 PositiveInteger](#1342-positiveinteger)
  - [13.43 SepColorIdPac](#1343-sepcoloridpac)
  - [13.44 SepEecIdPac](#1344-sepeecidpac)
  - [13.45 SourceMacAddressLimit](#1345-sourcemacaddresslimit)
  - [13.46 SyncModePerLink](#1346-syncmodeperlink)
  - [13.47 TaggedL2cpProcessing](#1347-taggedl2cpprocessing)
  - [13.48 TimeIntervalT](#1348-timeintervalt)
  - [13.49 TimeAndDate](#1349-timeanddate)
  - [13.50 TimeIntervalUnit](#1350-timeintervalunit)
  - [13.51 VlanId](#1351-vlanid)
  - [13.52 VlanIdListing](#1352-vlanidlisting)
  - [13.53 VlanIdListOrUntag](#1353-vlanidlistoruntag)
  - [13.54 VlanIdMappingType](#1354-vlanidmappingtype)
  - [13.55 VlanIdMappingTypeOrUntag](#1355-vlanidmappingtypeoruntag)
  - [13.56 VlanIdPreservation](#1356-vlanidpreservation)
- [14. Legato Service Order for Carrier Ethernet Services](#14-legato-service-order-for-carrier-ethernet-services)
  - [14.1 Legato Envelope and MEF Payload Association](#141-legato-envelope-and-mef-payload-association)
- [15. References](#15-references)

<p style="page-break-before:always;"></p>


# 1. List of Contributing Members

The following members of the MEF participated in the development of this document and have requested to be included in this list.

<p style="page-break-before:always;"></p>

# 2. Abstract and Introduction

This MEF Standard consisting of this Develop Guide and its associated software artifacts (JSON Schemas) defines and describes the product-specific payload for the LSO-Legato API for the Carrier Ethernet services. The document starts with an overview of LSO-Legato and the Carrier Ethernet Subscriber and Operator services. It then provides a basic information model for the MEF Carrier Ethernet Service Attributes including tables of all of the Service Attributes supported by all of the Subscriber and Operator Carrier Ethernet payloads along the the characteristics of each. The final sections describe the Data Model in both a technology-independent way and a technology-specific way focused on JSON. The JSON model, itself, is an independent software artifact.

This document can be thought of as a "developer's guide" for the API. MEF Services are described by a set of Service Attributes, specific information that is agreed between the provider and the user of the service, that describes some aspect of the service behavior or capability. The document the describes the Service Attributes usef for Subscriber (EVC-based) and Operator (OVC-Based) services. Carrier Ethernet service attributes are defined in MEF 10.4 and MEF 26.2.

The following sections provide background on Lifecycle Services Orchestration and Carrier Ethernet services. This is followed by an abbreviated information model that describes how the Service Attributes of MEF Carrier Ethernet Services are organized. A technology-independent overview of the data model is presented followed by an overview of the actual JSON Schemas. After this are tables of the Service Attributes that include the Service Attribute Name, JSON Name, description, the reference to the MEF standard and section, data type, and, when appropriate, validation notes that describe relationships between the various Service Attributes.

<p style="page-break-before:always;"></p>

# 3. Terminology and Abbreviations

This section defines the terms used in this document. In many cases, the normative definitions to terms are found in other documents. In these cases, the third column is used to provide the reference that is controlling, in other MEF or external documents. If the reference includes an asterisk (*), the definition has been adapted from the original.<br /> <br />

<TABLE style="border:solid; border-width:1px; border-color:#aaaaaa; padding:4px;border-collapse: collapse; ">
<TR style="background-color:blue"><TD style="width:25%; text-align:center"><strong>Term</strong></TD><TD style="width:50%; text-align:center"><strong>Definition</strong></TD><td style="width:20%; text-align:center"><strong>Reference</strong></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Business Applications</TD>
<TD>The Service Provider functionality supporting Business Management Layer functionality (e.g., product catalog, ordering, billing, relationship management, etc.)</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+55+-+LSO+Reference+Architecture">MEF 55</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>BUS</TD>
<TD>See <i>Business Applications</i></TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+55+-+LSO+Reference+Architecture">MEF 55</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>ENNI</TD>
<TD>A reference point representing the boundary between two Operator Carrier Ethernet Networks that are operated as separate administrative domains.</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+26.2+-+ENNI+and+Operator+Service+Attributes">MEF 26.2</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Ethernet Service Provider</TD>
<TD>An organization that provides to a Subscriber a connectivity service that carries Ethernet Frames irrespective of the underlying technology and that is specified using Service Attributes as defined in a MEF Standard.</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes">MEF 10.4  *</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Ethernet UNI</TD>
<TD>The demarcation point between the responsibility of the Ethernet Service Provider and the Ethernet Service Subscriber (cf. Operator UNI)</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes">MEF 10.4 </a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>EVC</TD>
<TD>An association of EVC End Points</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes">MEF 10.4 </a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>EVC End Point</TD>
<TD>A construct at a (Ethernet) UNI that selects a subset of the Service Frames that pass over the UNI.</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes">MEF 10.4 </a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>External Interface</TD>
<TD>Either a UNI or an ENNI.</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+4+-+MEN+Architecture+Framework">MEF 4</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Operator UNI</TD>
<TD>A UNI associated associated by an OVC End Point (cf. Ethernet UNI)</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+26.2+-+ENNI+and+Operator+Service+Attributes">MEF 26.2</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Operator Virtual Connection</TD>
<TD>An association of OVC End Points</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+26.2+-+ENNI+and+Operator+Service+Attributes">MEF 26.2</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>OVC</TD>
<TD>See <i>Operator Virtual Connection</i></TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+26.2+-+ENNI+and+Operator+Service+Attributes">MEF 26.2</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>OVC End Point</TD>
<TD>An association of an OVC with a specific External Interface, i.e., Operator UNI or ENNI.</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+26.2+-+ENNI+and+Operator+Service+Attributes">MEF 26.2</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Service Attribute</TD>
<TD>Specific information that is agreed between the provider and the user of the service, that describes some aspect of the service behavior or capability.</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes">MEF 10.4</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Service Provider</TD>
<TD>In the context of this document, a Service Provider is an Ethernet Service Provider.</TD>
<TD style="text-align:center">This Document</TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Service Orchestration Functionality</TD>
<TD></TD>
<TD style="text-align:center">This Document</TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>Subscriber</TD>
<TD>In the context of this document, the end-user of an Ethernet Service.</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes">MEF 10.4  *</a></TD></TR>

<TR style="border-width: 1px; border-style: solid; border-color: grey">
<TD>UNI</TD>
<TD>An Ethernet UNI or an Operator UNI depending on context</TD>
<TD style="text-align:center"><a href="https://wiki.mef.net/display/CESG/MEF+26.2+-+ENNI+and+Operator+Service+Attributes">MEF 26.2</a></TD></TR>

</TABLE>

<p style="page-break-before:always;"></p>

# 4. Overview of LSO-Legato

[MEF 55](https://wiki.mef.net/display/CESG/MEF+55+-+LSO+Reference+Architecture) describes the Reference Architecture for Lifecycle Service Orchestration (LSO) of MEF-defined connectivity services. MEF 55 defines seven LSO Reference Points that are abstract interconnection points between different domains - either within the service provider domain (intra-domain) or between service provider and other business entities (inter-domain). One of these LSO Reference Points is LSO Legato which defines the abstract boundary point between a Service Provider's or Partner's Business Application (BA) and Service Orchestration Functionality (SOF) for providing connectivity services provisioning.

| <img width="727" height="313" src="media/lsoReferenceArchitecture.png" alt="LSO Picture" /> |
|:--:|
| <i>Figure 1 - LSO Reference Architecture</i> |

The access to automated service provisioning functionality is provided using the Service Provisioning API at LSO Legato. LSO Legato provides a suite of APIs for provisioning, inventory, performance management which are standardized by MEF as LSO Legato APIs, and which are made available by MEF in a series of releases of the LSO Legato SDK.

The LSO Legato APIs comprise two parts: one is the service-independent functionality, or Basic API Structure, and the second is the service-specific payload, or Information Payload, as shown in diagram below.

| <img src="media/envelopePayload.png" alt="T_M Forum" name="T_M Forum_Envelope" /> |
|:--:|
| <i>Figure 2 - TMForum API Envelope/MEF Payload</i> |

This document defines the service-specific payload, shown as JSON Data Model in the figure above, specifically for a MEF 3.0 Subscriber and Operator services as defined in [MEF 10.4] (https://wiki.mef.net/display/CESG/MEF10.4+) and [MEF 26.2] (https://wiki.mef.net/display/CESG/MEF26.2).

The envelope resources of the API and association to specific payload resources will be discussed in detail later in this document.

<p style="page-break-before:always;"></p>

# 5. Superclasses and Resources in support of Subscriber and Operator Carrier Ethernet Services

There are common attributes shared between each of the three main resources across EVC and OVC services. The MEF Service Model Information Model - Carrier Ethernet [MEF 7.4] defines three super classes:

- CarrierEthernetExternalInterface
- CarrierEthernetServiceEndPoint
- CarrierEthernetService

CarrierEthernetExternalInterface is a superclass for EVC Service CarrierEthernetUni and CarrierEthernetEnni. The inherited relationship between the EVC and OVC objects and the respective superclasses are described later in this document.  The inheritence relationship in the information model is mapped to the schema using the 'allOf' keyword.

# 6. Overview of Subscriber Ethernet Services

A Subscriber Ethernet Service is built on an Ethernet Virtual Connection (EVC) which is an association of two or more Subscriber Ethernet UNIs. More specifically an EVC is associated with two or more EVC End Points. Each EVC End Point is associated with a Subscriber UNI, so externally the EVC looks like an association of UNIs. EVCs and their Service Attributes are described in [MEF 10.4](https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes).

| <img width="728" height="318" src="media/evcServiceModel.png" alt="" name="" /> |
|:--:|
| <i>Figure 3 - EVC Service Model</i> |

A CarrierEthernetSubscriber UNI is a subclass of abstract class, CarrierEthernetUni.  CarrierEthernetUni is a subclass of CarrierEthernetExternalInterface. CarrierEthernetEndPoint is a subclass of CarrierEthernetServiceEndPoint.  CarrierEthernetEvc is a subclass of CarrierEthernetService.  The corresponding schemas leverage the 'allOf' keyword in order to support polymorphism.

# 7. Overview of Operator Ethernet Services

An Operator Ethernet Service is built on an Operator Virtual Connection (OVC). An OVC has an assocition with two or more OVC End Points.  OVC End Points are associated with ENNI, Operator UNIs, and Virtual UNIs. OVCs and their Service Attributes are described in [MEF 26.2](https://wiki.mef.net/display/CESG/MEF+26.2+-+Operator+Ethernet+Service+Attributes).

| <img width="728" height="318" src="media/ovcServiceModel.png" alt="" name="" /> |
|:--:|
| <i>Figure 4 - OVC Service Model</i> |

Each of the OVC main classes are sub-classed from a parent class that holds common attributes that are used by similar classes in the EVC model. The main OVC classes are CarrierEthernetEnniService, CarrierEthernetEnni, CarrierEthernetVuni, CarrierEthernetOperatorUni, CarrierEthernetOvcEndPoint and CarrierEthernetOvc. The superclasses are CarrierEthernetExternalInterface, CarrierEthernetServiceEndPoint, CarrierEthernetService and CarrierEthernetUni.

The Network Operators connect to each other at ENNIs and each OVC delivers Ethernet Frames between the various External Interfaces, UNIs and ENNIs, within the Network Operator's footprint. So, whereas an EVC associates a set of UNIs, an OVC associates one or more E-NNIs and zero or more UNIs.

# 8. Data Model Design Principles

The design for the API Schema is based on a number of assumptions

1. The requirements for which attributes are necessary at Service Order, Inventory and other APIs in future will use the same schemas.  Specifically, there currently are not separated schemas for each functional area.

2. A service order must support multiple service order items.  A service order item includes CarrierEthernetSubscriberUni, CarrierEthernetEvcEndPoint and CarrierEthernetEvc for Subscriber Ethernet Services.  A service order item includes CarrierEthernetOperatorUni, CarrierEthernetEnniService, CarrierEthernetVuni, CarrierEthernetOvcEndPoint and CarrierEthernetOvc for Operator Ethernet Services.

3. The common resources are stored in a Carrier Ethernet Common schema and is available for both Subscriber and Operator Ethernet Service schemas.

4. The use of common attributes are supported using superclasses in an information model. Analogously, the schemas support polymorphism using the 'allOf' keyword in the schemas.

5. For the main resources in both the Subscriber Ethernet and Operator Ethernet schemas there exists two-way relationships.  The reference pattern detailed later in the document is used.

# 9. Data Models for Carrier Ethernet Subscriber and Operator Services

The Legato API is based on the TMForum API format approach with a service-agnostic envelope and a service-specific payload.  The envelope part of the API defines service agnostic Order Items.  The payload part of the API defines service specific resources.

## 9.1 Service Order and Carrier Ethernet Associations

The Carrier Ethernet Service resources for both Subscriber and Operator Carrier Ethernet Services are positioned in the payload. The association between the Legato Service Order Envelope Service Order Items and the Carrier Ethernet Services resources is illustrated in the figure below.

<center>
<img src="media/envelopeAndPayload.png" alt="EnvPay"  />
</center>
<center><i>Figure 3 - Legato Service Order Envelope/MEF Payload Association</i></center>

The developer will make the association between an Envelope Service Order Item and a specific Carrier Ethernet resource by instantiating a sub-classed MefServiceConfiguration. Sub-classed MefServiceConfiguration objects or resources include the set of Subscriber Carrier Ethernet and Operator Carrier Ethernet Service objects (resources).

The envelope has two main objects, Service Order and Service Order Item. A Service Order can have one or many Service Order Items. The payload depends on the specific Carrier Ethernet service intending to be activated.  

<center>
<img src="media/carrierEthernetExtension.png" alt="EtherExt"  />
</center>
<center><i>Figure 4 - Carrier Ethernet Extension</i></center>

## 9.2. Organization and Structure of the JSON Schemas

The organization and structure of the Schemas are in the following directory structure including schema file names:

spec/legato:

- carrierEthernetCommon.yaml
- carrierEthernetOvc.yaml
- carrierEthernetEnni.yaml
- carrierEthernetOperatorUni.yaml
- carrierEthernetEvc.yaml
- carrierEthernetSubscriberUni.yaml
- carrierEthernetVirtualUni.yaml
  
### 9.2.1 CarrierEthernetSubscriberUni-CarrierEthernetEvcEndPoint Relationship

The following section discusses the mapping of the information model object relationship between Subscriber UNI and EVC End Point to the schema.

| <img width="728" height="318" src="media/subscriberUniEvcEndPointRelationship.png" alt="" name="" /> |
|:--:|
| <i>Figure 5 - CarrierEthernetSubscriberUni:CarrierEthernetEvcEndPoint Relationship</i> |

### 9.2.2 CarrierEthernetEvc-CarrierEthernetEvcEndPoint Relationship

The following section discusses the mapping of the information model object relationship between Subscriber UNI and EVC End Point to the schema.

| <img width="728" height="318" src="media/evcEvcEndPointRelationship.png" alt="" name="" /> |
|:--:|
| <i>Figure 6 - CarrierEthernetEvc:CarrierEthernetEvcEndPoint Relationship</i> |
NOTE: Similar relationships and corresponding mappings exist for Operator Ethernet Services and corresponding objects/resources.

# 10. Carrier Ethernet Superclass and Attributes

The following section defines the set of superclasses that are used by the Carrier Ethernet services.  The superclass resource with associated attributes defined are:

- CarrierEthernetExternalInterface Service Attributes,
- CarrierEthernetServiceEndPoint Service Attributes,
- CarrierEthernetService Service Attributes,
- CarrierEthernetUni Service Attributes
  
These are superclasses in support of CarrierEthernetEnni, CarrierEthernetSubscriberUni, CarrierEthernetOperatorUni, CarrierEthernetEvcEndPoint, CarrierEthernetOvcEndPoint, CarrierEthernetEvc and CarrierEthernetOvc which are detailed later in the document.

## 10.1 CarrierEthernetExternalInterface Service Attributes

The CarrierEthernetExternalInterface represents the physical or virtual Ethernet interface used for Ethernet services.  It contains the common attributes of ENNI, Subscriber UNI and Operator UNI.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**admininstrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**externalInterfaceframeFormat** | [**EthernetFrameFormat**](EthernetFrameFormat.md) |  | [optional] [default to null]
**linkOam** | [**EnabledDisabled**](EnabledDisabled.md) | Controls when and how Link OAM per IEEE Std 802.3-2015 is run on the physi-cal links in the External Interface. Refer-ence MEF 10.4 Section 9.13 Subscriber UNI Link OAM Service Attribute, MEF 26.2 Section 9.9 ENNI Link OAM Common Attribute and MEF 26.2 Section 14.14 Operator UNI Link OAM Service Attribute. | [optional] [default to null]
**l2cpPeering** | [**List**](L2cpPeering.md) | Specifies the Layer 2 Control Protocols that are peered at the EI, as described in MEF 45.1. Reference MEF 10.4 Section 9.17 Subscriber UNI L2CP Peering Service Attribute, MEF 26.2 Section 10.1 ENNI L2CP Peering Multilateral Attribute.  L2CP Peering applied to UNI and MEF 26.2 Section 14.21 Operator UNI L2CP Peering Service Attribute. | [optional] [default to null]
**lagLinkMeg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a LAG link MEG is instantiated on each physical link in the EI, if the EI has more than one physical link. Reference MEF 10.4 Section 9.15 Subscriber UNI LAG Link MEG Service Attribute, MEF 26.2 Section 9.8 ENNI LAG Link MEG Common Attribute and MEF 26.2 Section 14.16 Operator UNI LAG Link MEG Service Attribute. | [optional] [default to null]
**meg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a MEP is instantiated at the EI for the UNI MEG or ENNI MEG. Reference MEF 10.4 Section 9.14 Sub-scriber UNI MEG Service Attribute, MEF 26.2 Section 9.7 ENNI MEG Common Attribute and MEF 26.2 Section 14.15 Operator UNI MEG Service Attribute. | [optional] [default to null]
**aggregationLinkMap** | [**List**](ConversationIdToAggregationLinkMap.md) |  | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Specifies the maximum size of EI Frames that can be transmitted across EI. Reference MEF 10.4 Section 9.8 Subscriber UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 14.8 Operator UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 10.3 ENNI Maximum Frame Size Multilateral Attribute. | [optional] [default to null]
**linkAggregation** | [**LinkAggregation**](LinkAggregation.md) |  | [optional] [default to null]

## 10.2 CarrierEthernetServiceEndPoint Service Attributes

The CarrierEthernetServiceEndPoint represents the EVC End Point or the OVC End Point.  This is an abstract class and the superclass of CarrierEthernetEvcEndPoint and OvcEndPoint.  It contains the common attributes of CarrierEthernetEvcEndPoint and OvcEndPoint.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**ingressClassOfServiceMap** | [**CosMap**](CosMap.md) |  | [optional] [default to null]
**colorMap** | [**ColorIdentifier**](ColorIdentifier.md) |  | [optional] [default to null]
**ingressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all ingress EI Frames mapped to the OVC End Point or EVC End Point. Reference MEF 26.2 Section 16.10 Ingress Band-width Profile per OVC End Point Service Attribute. Reference MEF 10.4 Section 10.8 EVC EP Ingress Bandwidth Profile Service Attribute. The absence of this attribute corresponds to a Service Attrib-ute of None. | [optional] [default to null]
**ingressBandwidthProfilePerCosName** | [**List**](BandwidthProfilePerClassOfServiceName.md) | For each CoS Name listed, Bandwidth Profile Flow parameters for all ingress EI Frames mapped to that CoS Name at the EVC End Point or OVC End Point. Reference MEF 26.2 Section 16.12 Ingress Bandwidth Profile per Class of Service Name Service and MEF 10.4 Section 10.9 EVC EP Class of Service Name Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**sourceMacAddressLimit** | [**List**](SourceMacAddressLimit.md) | Specifies a limit on the number of differ-ent Source MAC address for which in-gress EI Frames at this EVC End Point or OVC End Point will be delivered. The absence of this attribute corresponds to a Service Attribute value of None. Refer-ence MEF 10.4 Section 10.12 EVC EP Source MAC Address Limit Service At-tribute and MEF 26.2 Section 16.15 OVC End Point Source MAC Address Limit Service Attribute. | [optional] [default to null]

## 10.3 CarrierEthernetService Service Attributes

The CarrierEthernetService represents the EVC or the OVC.  This is an abstract class and the superclass of Evc and Ovc.  It contains the common attributes of Evc and Ovc.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**cTagPcpPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the PCP field in the C-Tag in Ingress EI Frames is preserved when the Egress EI Frame also has a C-Tag. Reference MEF 26.2 Section 12.8 OVC CE-VLAN PCP Preservation Service Attribute and MEF 10.4 Section 8.5 EVC C-Tag PCP Preservation Service Attribute. | [optional] [default to null]
**cTagDeiPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the DEI field in the C-Tag in Ingress Frames is preserved when the Egress EI Frame also has C-Tag. Reference MEF 26.2 Section 12.9 OVC CE-VLAN ID DEI Preservation Service Attribute and MEF 10.4 Section 8.6 EVC C-Tag DEI Preservation Service Attribute. | [optional] [default to null]
**connectionType** | [**ConnectionType**](ConnectionType.md) |  | [optional] [default to null]
**frameDisposition** | [**FrameDisposition**](FrameDisposition.md) |  | [optional] [default to null]
**listOfCosNames** | [**List**](string.md) | Used to specify all the Class of Service Names supported by an EVC or OVC. Reference MEF 10.4 Section 8.7 EVC List of Class of Service Names Service Attribute. The Class of Service Names supported by the OVC. Reference MEF 26.2 Section 12.12 OVC List of Class of Service Names Service Attribute. | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Maximum size of EI frames that can be carried over the EVC or OVC. Reference MEF 10.4 Section 8.10 EVC Maximum Service Frame Size Service Attribute and MEF 26.2 Section 12.6 OVC Maximum Frame Size Service Attribute. | [optional] [default to null]
**availableMegLevel** | [**List**](MegLevel.md) | The lowest MEG level for which SOAM Frames are not peered or discarded by the SP or Operator. If this attribute is not present there is no such level (that is, SOAM frames are all MEG levels may be peered or discarded by the SP or Opera-tor). Reference MEF 10.4 Section 8.11 EVC Available MEG Level Service Attribute and MEF 26.2 Section 12.15 OVC Available MEF Level Service Attribute. | [optional] [default to null]
**carrierEthernetSls** | [**List**](carrierEthernetSls.md) | Technical details of the service level in terms of Performance Objectives, agreed between the Service Provider and the Subscriber or between Service Provider and the Operator as part of the Service Level Agreement. A given SLS might contain 0,1 or more Performance Objec-tives for each Performance Metric.  Ref-erence MEF 10.4 Section 8.8 EVC Service Level Specification Service Attribute and MEF 26.2 Section 12.13 OVC Service Level Specification Service Attribute. | [optional] [default to null]

## 10.4 CarrierEthernetUni Service Attributes

The Uni represents the Physical Interface used for Ethernet services with common attributes. This is an abstract class and the super class. It contains the common attributes of Operator UNI and Subscriber UNI.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**maximumNumberOfEndPoints** | [**Integer**](integer.md) | An integer greater than or equal to 1 that limits the number of EVC End Points that can be located at the UNI. Reference MEF 10.4 Section 9.9 Subscriber UNI Maximum Number of EVC EPs Service Attribute. The maximum number of OVC End Points that the Operator CEN can support at the UNI.  Reference MEF 26.2 Section 14.10 Operator UNI Maximum Number of OVC End Points Service Attribute. | [optional] [default to null]
**maxNumOfCtagVlanIdsPerEndPoint** | [**Integer**](integer.md) | An integer greater than or equal to 1 that limits the number of C-Tag VLAN IDs that can map to each EVC End Point. Reference MEF 10.4 Section 9.10 Subscriber UNI Maximum Number of C-Tag VLAN IDs per EVC EP Service Attribute. The maximum number of CE-VLAN ID values that can be mapped to an OVC End Point by the Operator CEN at the UNI. Reference MEF 26.2 Section 14.11 Operator UNI Maximum Number of CE-VLAN IDs per OVC End Point Service Attribute. | [optional] [default to null]
**tokenShare** | [**EnabledDisabled**](EnabledDisabled.md) | An attribute that indicates whether Band-width Profile Envelopes containing more than one Bandwidth Profile Flow are supported by the Service Provider at the Subscriber UNI or Operator UNI. Reference MEF 10.4 Section 9.11 Subscriber UNI Token Share Service Attribute or MEF 26.2 Section 14.18 Operator UNI Token Share Service Attribute. | [optional] [default to null]
**envelopes** | [**List**](Envelope.md) | The Envelopes and Envelope Coupling Flag values to which Bandwidth Profile Flows can be mapped. Reference MEF 10.4 Section 9.12 Sub-scriber UNI Envelopes Service Attribute and MEF 26.2 Section 14.19 Operator UNI Envelopes Service Attribute. | [optional] [default to null]
**l2cpAddressSet** | [**L2cpAddressSet**](L2cpAddressSet.md) | L2CP Address Set Service Attribute is defined in MEF 45.1. Reference MEF 10.4 Section 9.16 Subscriber UNI L2CP Address Set Ser-vice Attribute and MEF 26.2 Section 14.20 Operator UNI L2CP Address Set Service Attribute. | [optional] [default to null]
**admininstrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**externalInterfaceframeFormat** | [**EthernetFrameFormat**](EthernetFrameFormat.md) |  | [optional] [default to null]
**linkOam** | [**EnabledDisabled**](EnabledDisabled.md) | Controls when and how Link OAM per IEEE Std 802.3-2015 is run on the physi-cal links in the External Interface. Refer-ence MEF 10.4 Section 9.13 Subscriber UNI Link OAM Service Attribute, MEF 26.2 Section 9.9 ENNI Link OAM Common Attribute and MEF 26.2 Section 14.14 Operator UNI Link OAM Service Attribute. | [optional] [default to null]
**l2cpPeering** | [**List**](L2cpPeering.md) | Specifies the Layer 2 Control Protocols that are peered at the EI, as described in MEF 45.1. Reference MEF 10.4 Section 9.17 Subscriber UNI L2CP Peering Service Attribute, MEF 26.2 Section 10.1 ENNI L2CP Peering Multilateral Attribute.  L2CP Peering applied to UNI and MEF 26.2 Section 14.21 Operator UNI L2CP Peering Service Attribute. | [optional] [default to null]
**lagLinkMeg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a LAG link MEG is instantiated on each physical link in the EI, if the EI has more than one physical link. Reference MEF 10.4 Section 9.15 Subscriber UNI LAG Link MEG Service Attribute, MEF 26.2 Section 9.8 ENNI LAG Link MEG Common Attribute and MEF 26.2 Section 14.16 Operator UNI LAG Link MEG Service Attribute. | [optional] [default to null]
**meg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a MEP is instantiated at the EI for the UNI MEG or ENNI MEG. Reference MEF 10.4 Section 9.14 Sub-scriber UNI MEG Service Attribute, MEF 26.2 Section 9.7 ENNI MEG Common Attribute and MEF 26.2 Section 14.15 Operator UNI MEG Service Attribute. | [optional] [default to null]
**aggregationLinkMap** | [**List**](ConversationIdToAggregationLinkMap.md) |  | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Specifies the maximum size of EI Frames that can be transmitted across EI. Reference MEF 10.4 Section 9.8 Subscriber UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 14.8 Operator UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 10.3 ENNI Maximum Frame Size Multilateral Attribute. | [optional] [default to null]
**linkAggregation** | [**LinkAggregation**](LinkAggregation.md) |  | [optional] [default to null]

# 11. Subscriber Ethernet Services

The following section provides the resources and corresponding attributes in support of Subscriber Ethernet Services.  The five main resources are:

- CarrierEthernetSubscriberUni Service Attributes
- CarrierEthernetSubscriberUniRef Attributes
- CarrierEthernetEvcEndPoint Service Attributes
- CarrierEthernetEvcEndPointRef Attributes
- CarrierEthernetEvc Service Attributes
- CarrierEthernetEvcRef Attributes
- 
## 11.1 CarrierEthernetSubscriberUni Service Attributes

The Ethernet User Network Interface demarcation point between the responsibility of the Service Provider and the responsibility of the Subscriber. Reference MEF 10.4 Section 9. Subscriber UNI Service Attributes.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | String that is used to allow the Subscriber and Service Provider to uniquely identify the UNI for operations purposes. Reference MEF 10.4 Section 9.1 Subscriber UNI ID Service Attribute. | [optional] [default to null]
**instantiation** | [**String**](string.md) | The value is either Physical or Virtual. Reference MEF 10.4 Section 9.2 Subscriber UNI Instantiation Service Attribute. | [optional] [default to null]
**listOfPhyLinks** | [**List**](SubscriberUniPhysicalLinks.md) |  | [optional] [default to null]
**virtualFrameMap** | [**List**](object.md) |  | [optional] [default to null]
**evcEndPoint** | [**List**](CarrierEthernetEvcEndPointRef.md) |  | [optional] [default to null]
**admininstrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**externalInterfaceframeFormat** | [**EthernetFrameFormat**](EthernetFrameFormat.md) |  | [optional] [default to null]
**linkOam** | [**EnabledDisabled**](EnabledDisabled.md) | Controls when and how Link OAM per IEEE Std 802.3-2015 is run on the physi-cal links in the External Interface. Refer-ence MEF 10.4 Section 9.13 Subscriber UNI Link OAM Service Attribute, MEF 26.2 Section 9.9 ENNI Link OAM Common Attribute and MEF 26.2 Section 14.14 Operator UNI Link OAM Service Attribute. | [optional] [default to null]
**l2cpPeering** | [**List**](L2cpPeering.md) | Specifies the Layer 2 Control Protocols that are peered at the EI, as described in MEF 45.1. Reference MEF 10.4 Section 9.17 Subscriber UNI L2CP Peering Service Attribute, MEF 26.2 Section 10.1 ENNI L2CP Peering Multilateral Attribute.  L2CP Peering applied to UNI and MEF 26.2 Section 14.21 Operator UNI L2CP Peering Service Attribute. | [optional] [default to null]
**lagLinkMeg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a LAG link MEG is instantiated on each physical link in the EI, if the EI has more than one physical link. Reference MEF 10.4 Section 9.15 Subscriber UNI LAG Link MEG Service Attribute, MEF 26.2 Section 9.8 ENNI LAG Link MEG Common Attribute and MEF 26.2 Section 14.16 Operator UNI LAG Link MEG Service Attribute. | [optional] [default to null]
**meg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a MEP is instantiated at the EI for the UNI MEG or ENNI MEG. Reference MEF 10.4 Section 9.14 Sub-scriber UNI MEG Service Attribute, MEF 26.2 Section 9.7 ENNI MEG Common Attribute and MEF 26.2 Section 14.15 Operator UNI MEG Service Attribute. | [optional] [default to null]
**aggregationLinkMap** | [**List**](ConversationIdToAggregationLinkMap.md) |  | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Specifies the maximum size of EI Frames that can be transmitted across EI. Reference MEF 10.4 Section 9.8 Subscriber UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 14.8 Operator UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 10.3 ENNI Maximum Frame Size Multilateral Attribute. | [optional] [default to null]
**linkAggregation** | [**LinkAggregation**](LinkAggregation.md) |  | [optional] [default to null]

## 11.2 CarrierEthernetSubscriberUniRef Service Attributes

Pointer to CarrierEthernetSubscriberUni resource.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**href** | [**URI**](URI.md) |  | [optional] [default to null]
**id** | [**UUID**](UUID.md) |  | [optional] [default to null]

## 11.3 CarrierEthernetEvcEndPoint Service Attributes

A CarrierEthernetEvcEndPoint is a construct at a UNI that selects a subset of the Service Frames that pass over the UNI. A CarrierEthernetEvcEndPoint represents the logical attachment of an Evc to a UNI. Reference MEF 10.4 Section 10 EVC EP Service Attributes.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | A string that is used to allow the Subscriber and Service Provider to uniquely identify the EvcEndPoint for operations purposes. Reference MEF 10.4 Section 10.1 EVC EP ID Service Attribute. | [optional] [default to null]
**role** | [**EvcEndPointRole**](EvcEndPointRole.md) | Indicates how EI Frames mapped to the EVC End Point can be forwarded.  Reference MEF 10.4 Section 10.3 EVC EP Role Service Attribute. | [optional] [default to null]
**egressBandwidthProfilePerEndPoint** | [**List**](EgressBwpFlow.md) | Attribute used to limit the rate of all Egress Service Frames mapped to an EVC EP at a UNI. Reference MEF 10.4 Section 10.10 EVC EP Egress Bandwidth Profile Service Attribute. | [optional] [default to null]
**egressBandwidthProfilePerCosName** | [**List**](ClassOfServiceEgressBandwidthProfile.md) | Used to limit the rate of all Egress Service Frames with a given Class of Service Name, as determined at the ingress UNI for each frame per the EVC EP Ingress Class of Service Map Service Attribute. Reference MEF 10.4 Section 10.11 EVC EP Class of Service Name Egress Band-width Profile Service Attribute. | [optional] [default to null]
**egressMap** | [**List**](EvcEpEgressMap.md) |  | [optional] [default to null]
**evcEndPointMap** | [**VlanIdListOrUntag**](VlanIdListOrUntag.md) |  | [optional] [default to null]
**subscriberMegMip** | [**MegLevel**](MegLevel.md) |  | [optional] [default to null]
**carrierEthernetSubscriberUni** | [**CarrierEthernetSubscriberUniRef**](CarrierEthernetSubscriberUniRef.md) |  | [optional] [default to null]
**evc** | [**CarrierEthernetEvcRef**](CarrierEthernetEvcRef.md) |  | [optional] [default to null]
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**ingressClassOfServiceMap** | [**CosMap**](CosMap.md) |  | [optional] [default to null]
**colorMap** | [**ColorIdentifier**](ColorIdentifier.md) |  | [optional] [default to null]
**ingressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all ingress EI Frames mapped to the OVC End Point or EVC End Point. Reference MEF 26.2 Section 16.10 Ingress Band-width Profile per OVC End Point Service Attribute. Reference MEF 10.4 Section 10.8 EVC EP Ingress Bandwidth Profile Service Attribute. The absence of this attribute corresponds to a Service Attrib-ute of None. | [optional] [default to null]
**ingressBandwidthProfilePerCosName** | [**List**](BandwidthProfilePerClassOfServiceName.md) | For each CoS Name listed, Bandwidth Profile Flow parameters for all ingress EI Frames mapped to that CoS Name at the EVC End Point or OVC End Point. Reference MEF 26.2 Section 16.12 Ingress Bandwidth Profile per Class of Service Name Service and MEF 10.4 Section 10.9 EVC EP Class of Service Name Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**sourceMacAddressLimit** | [**List**](SourceMacAddressLimit.md) | Specifies a limit on the number of differ-ent Source MAC address for which in-gress EI Frames at this EVC End Point or OVC End Point will be delivered. The absence of this attribute corresponds to a Service Attribute value of None. Refer-ence MEF 10.4 Section 10.12 EVC EP Source MAC Address Limit Service At-tribute and MEF 26.2 Section 16.15 OVC End Point Source MAC Address Limit Service Attribute. | [optional] [default to null]

## 11.4 CarrierEthernetEvcEndPointRef Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**evcRef** | [**CarrierEthernetEvcRef**](CarrierEthernetEvcRef.md) |  | [optional] [default to null]
**id** | [**UUID**](UUID.md) | Points to CarrierEthernetEvcEndPoint | [optional] [default to null]

## 11.5 CarrierEthernetEvc Service Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | Used to identify an EVC within the SP Network. Reference MEF 10.4 Section 8.1 EVC ID Service Attribute. | [optional] [default to null]
**evcEndPoints** | [**List**](CarrierEthernetEvcEndPoint.md) | Pointer to EvcEndPoint. | [optional] [default to null]
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**cTagPcpPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the PCP field in the C-Tag in Ingress EI Frames is preserved when the Egress EI Frame also has a C-Tag. Reference MEF 26.2 Section 12.8 OVC CE-VLAN PCP Preservation Service Attribute and MEF 10.4 Section 8.5 EVC C-Tag PCP Preservation Service Attribute. | [optional] [default to null]
**cTagDeiPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the DEI field in the C-Tag in Ingress Frames is preserved when the Egress EI Frame also has C-Tag. Reference MEF 26.2 Section 12.9 OVC CE-VLAN ID DEI Preservation Service Attribute and MEF 10.4 Section 8.6 EVC C-Tag DEI Preservation Service Attribute. | [optional] [default to null]
**connectionType** | [**ConnectionType**](ConnectionType.md) |  | [optional] [default to null]
**frameDisposition** | [**FrameDisposition**](FrameDisposition.md) |  | [optional] [default to null]
**listOfCosNames** | [**List**](string.md) | Used to specify all the Class of Service Names supported by an EVC or OVC. Reference MEF 10.4 Section 8.7 EVC List of Class of Service Names Service Attribute. The Class of Service Names supported by the OVC. Reference MEF 26.2 Section 12.12 OVC List of Class of Service Names Service Attribute. | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Maximum size of EI frames that can be carried over the EVC or OVC. Reference MEF 10.4 Section 8.10 EVC Maximum Service Frame Size Service Attribute and MEF 26.2 Section 12.6 OVC Maximum Frame Size Service Attribute. | [optional] [default to null]
**availableMegLevel** | [**List**](MegLevel.md) | The lowest MEG level for which SOAM Frames are not peered or discarded by the SP or Operator. If this attribute is not present there is no such level (that is, SOAM frames are all MEG levels may be peered or discarded by the SP or Opera-tor). Reference MEF 10.4 Section 8.11 EVC Available MEG Level Service Attribute and MEF 26.2 Section 12.15 OVC Available MEF Level Service Attribute. | [optional] [default to null]
**carrierEthernetSls** | [**List**](carrierEthernetSls.md) | Technical details of the service level in terms of Performance Objectives, agreed between the Service Provider and the Subscriber or between Service Provider and the Operator as part of the Service Level Agreement. A given SLS might contain 0,1 or more Performance Objec-tives for each Performance Metric.  Ref-erence MEF 10.4 Section 8.8 EVC Ser-vice Level Specification Service Attribute and MEF 26.2 Section 12.13 OVC Service Level Specification Service Attribute. | [optional] [default to null]

## 11.6 CarrierEthernetEvcRef Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**href** | [**URI**](URI.md) |  | [optional] [default to null]
**id** | [**UUID**](UUID.md) |  | [optional] [default to null]

# 12. Operator Ethernet Services

The following section provides the resources and corresponding attributes in support of Operator Ethernet Services.  The six main resources are:

- CarrierEthernetOperatorUni Service Attributes
- CarrierEthernetVirtualUni Service Attributes
- CarrierEthernetVirtualUniRef Attributes
- CarrierEthernetEnni Service Attributes
- CarrierEthernetEnniService Service Attributes
- CarrierEthernetOvcEndPoint Service Attributes
- CarrierEthernetOvcEndPointRef Attributes
- CarrierEthernetOvc Service Attributes
- CarrierEthernetOvcRef Attributes

## 12.1 CarrierEthernetOperatorUni Service Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | An identifier for the UNI intended for management purposes. Reference MEF 26.2 Section 14.1 Operator UNI Identifier Service Attribute. | [optional] [default to null]
**synchronousMode** | [**List**](SyncModePerLink.md) |  | [optional] [default to null]
**numberOfLinks** | [**Integer**](integer.md) | The number of physical links at the UNI. Reference MEF 26.2 Section 14.4 Operator UNI Number of Links Service Attribute. | [optional] [default to null]
**physicalLayer** | [**List**](PhysicalLayer.md) | The physical layer of each of the links supporting the Operator UNI. Reference MEF 26.2 Section 14.2 Operator UNI Physical Layer Service Attribute. | [optional] [default to null]
**defaultCeVlanId** | [**VlanId**](VlanId.md) |  | [optional] [default to null]
**ingressBandwidthProfile** | [**List**](BwpFlow.md) |  | [optional] [default to null]
**egressBandwidthProfile** | [**List**](BwpFlow.md) |  | [optional] [default to null]
**elmi** | [**String**](string.md) |  | [optional] [default to null]
**ovcEndPoint** | [**List**](CarrierEthernetOvcEndPointRef.md) |  | [optional] [default to null]
**admininstrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**externalInterfaceframeFormat** | [**EthernetFrameFormat**](EthernetFrameFormat.md) |  | [optional] [default to null]
**linkOam** | [**EnabledDisabled**](EnabledDisabled.md) | Controls when and how Link OAM per IEEE Std 802.3-2015 is run on the physi-cal links in the External Interface. Refer-ence MEF 10.4 Section 9.13 Subscriber UNI Link OAM Service Attribute, MEF 26.2 Section 9.9 ENNI Link OAM Common Attribute and MEF 26.2 Section 14.14 Operator UNI Link OAM Service Attribute. | [optional] [default to null]
**l2cpPeering** | [**List**](L2cpPeering.md) | Specifies the Layer 2 Control Protocols that are peered at the EI, as described in MEF 45.1. Reference MEF 10.4 Section 9.17 Subscriber UNI L2CP Peering Service Attribute, MEF 26.2 Section 10.1 ENNI L2CP Peering Multilateral Attribute.  L2CP Peering applied to UNI and MEF 26.2 Section 14.21 Operator UNI L2CP Peering Service Attribute. | [optional] [default to null]
**lagLinkMeg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a LAG link MEG is instantiated on each physical link in the EI, if the EI has more than one physical link. Reference MEF 10.4 Section 9.15 Subscriber UNI LAG Link MEG Service Attribute, MEF 26.2 Section 9.8 ENNI LAG Link MEG Common Attribute and MEF 26.2 Section 14.16 Operator UNI LAG Link MEG Service Attribute. | [optional] [default to null]
**meg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a MEP is instantiated at the EI for the UNI MEG or ENNI MEG. Reference MEF 10.4 Section 9.14 Sub-scriber UNI MEG Service Attribute, MEF 26.2 Section 9.7 ENNI MEG Common Attribute and MEF 26.2 Section 14.15 Operator UNI MEG Service Attribute. | [optional] [default to null]
**aggregationLinkMap** | [**List**](ConversationIdToAggregationLinkMap.md) |  | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Specifies the maximum size of EI Frames that can be transmitted across EI. Reference MEF 10.4 Section 9.8 Subscriber UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 14.8 Operator UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 10.3 ENNI Maximum Frame Size Multilateral Attribute. | [optional] [default to null]
**linkAggregation** | [**LinkAggregation**](LinkAggregation.md) |  | [optional] [default to null]

## 12.2 CarrierEthernetVirtualUni Service Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**adminState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**identifier** | [**String**](string.md) | An identifier for the instance of the VUNI intended for operations purposes. | [optional] [default to null]
**sVlanId** | [**VlanId**](VlanId.md) |  | [optional] [default to null]
**defaultEnniCeVlanId** | [**VlanId**](VlanId.md) |  | [optional] [default to null]
**maximumNumberOfOvcEndPoints** | [**Integer**](integer.md) | The maximum number of OVC End Points that can be in the VUNI. | [optional] [default to null]
**maximumNumberOfEnniCeVlanIdsPerOvcEndPoint** | [**Integer**](integer.md) | The maximum number of ENNI CE-VLAN ID values that can be mapped to an OVC End Point that is in the VUNI. | [optional] [default to null]
**ingressBandwidthProfile** | [**List**](BwpFlow.md) | A Bandwidth Profile Flow for all ingress Frames mapped to the VUNI. Reference MEF 26.2 Section 15.1.6 VUNI Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**egressBandwidthProfile** | [**List**](BwpFlow.md) | A Bandwidth Profile Flow for all egress Frames mapped to the VUNI.  Reference MEF 26.2 Section 15.1.7 VUNI Egress Bandwidth Profile Service Attribute. | [optional] [default to null]
**l2cpAddressSet** | [**L2cpAddressSet**](L2cpAddressSet.md) |  | [optional] [default to null]
**l2cpPeering** | [**L2cpPeering**](L2cpPeering.md) |  | [optional] [default to null]
**mepList** | [**List**](MepLevelAndDirection.md) | The indication of the instantiation of a MEP. A list with each item specifying the MEG Level. Reference MEF 26.2 Section 15.1.10 VUNI Maintenance End Point List Service Attribute. | [optional] [default to null]
**ovcEndPoint** | [**List**](CarrierEthernetOvcEndPointRef.md) | Reference to CarrierEthernetOvcEndPoint. | [optional] [default to null]

## 12.3 CarrierEthernetVirtualUniRef Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**href** | [**URI**](URI.md) |  | [optional] [default to null]
**id** | [**UUID**](UUID.md) |  | [optional] [default to null]

## 12.4 CarrierEthernetEnni Service Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**peeringIdentifier** | [**String**](string.md) | An identifier for the ENNI intended for operations purposes by the interconnecting Operators at the ENNI. Reference MEF 26.2 Section 9.1 ENNI Peering Identifier Common Attribute. | [optional] [default to null]
**numberOfLinks** | [**Integer**](integer.md) | The number of physical links in the ENNI. Reference MEF 26.2 Section 9.4 ENNI Number of Links Common Attribute. | [optional] [default to null]
**taggedL2cpFrameProcessing** | [**TaggedL2cpProcessing**](TaggedL2cpProcessing.md) |  | [optional] [default to null]
**physicalLayer** | [**List**](PhysicalLayer.md) | The physical layer of each of the links supporting the ENNI. Reference MEF 26.1 Section 9.2 ENNI Physical Layer Common Attribute. | [optional] [default to null]
**enniService** | [**List**](CarrierEthernetEnniService.md) | Attribute pointing to CarrierEthernetEnniService. | [optional] [default to null]
**admininstrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**externalInterfaceframeFormat** | [**EthernetFrameFormat**](EthernetFrameFormat.md) |  | [optional] [default to null]
**linkOam** | [**EnabledDisabled**](EnabledDisabled.md) | Controls when and how Link OAM per IEEE Std 802.3-2015 is run on the physi-cal links in the External Interface. Refer-ence MEF 10.4 Section 9.13 Subscriber UNI Link OAM Service Attribute, MEF 26.2 Section 9.9 ENNI Link OAM Common Attribute and MEF 26.2 Section 14.14 Operator UNI Link OAM Service Attribute. | [optional] [default to null]
**l2cpPeering** | [**List**](L2cpPeering.md) | Specifies the Layer 2 Control Protocols that are peered at the EI, as described in MEF 45.1. Reference MEF 10.4 Section 9.17 Subscriber UNI L2CP Peering Service Attribute, MEF 26.2 Section 10.1 ENNI L2CP Peering Multilateral Attribute.  L2CP Peering applied to UNI and MEF 26.2 Section 14.21 Operator UNI L2CP Peering Service Attribute. | [optional] [default to null]
**lagLinkMeg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a LAG link MEG is instantiated on each physical link in the EI, if the EI has more than one physical link. Reference MEF 10.4 Section 9.15 Subscriber UNI LAG Link MEG Service Attribute, MEF 26.2 Section 9.8 ENNI LAG Link MEG Common Attribute and MEF 26.2 Section 14.16 Operator UNI LAG Link MEG Service Attribute. | [optional] [default to null]
**meg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a MEP is instantiated at the EI for the UNI MEG or ENNI MEG. Reference MEF 10.4 Section 9.14 Sub-scriber UNI MEG Service Attribute, MEF 26.2 Section 9.7 ENNI MEG Common Attribute and MEF 26.2 Section 14.15 Operator UNI MEG Service Attribute. | [optional] [default to null]
**aggregationLinkMap** | [**List**](ConversationIdToAggregationLinkMap.md) |  | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Specifies the maximum size of EI Frames that can be transmitted across EI. Reference MEF 10.4 Section 9.8 Subscriber UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 14.8 Operator UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 10.3 ENNI Maximum Frame Size Multilateral Attribute. | [optional] [default to null]
**linkAggregation** | [**LinkAggregation**](LinkAggregation.md) |  | [optional] [default to null]

## 12.5 CarrierEthernetEnniService Service Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**operatorEnnIdentifier** | [**String**](string.md) | An identifier for the ENNI intended for management purposes. Reference MEF 26.2 Section 13.1 Operator ENNI Identifier Service Attribute. | [optional] [default to null]
**svlanIdControl** | [**SvlanIdControl**](SvlanIdControl.md) |  | [optional] [default to null]
**maximumNumberOfOvcs** | [**Integer**](integer.md) | The maximum number of OVCs that the Operator CEN can support at the ENNI. Reference MEF 26.2 Section 13.3 Maximum Number of OVCs Service Attribute. | [optional] [default to null]
**maximumNumberOfOvcEndPointsPerOvc** | [**Integer**](integer.md) | The maximum number of OVC End Points that the Operator CEN can support at the ENNI for an OVC. Reference MEF 26.2 Section 13.4 Maximum Number of OVC End Points per OVC Service Attribute. | [optional] [default to null]
**tokenShare** | [**String**](string.md) | An indication of the support of mapping more than one Bandwidth Profile Flow to an Envelope at the ENNI. Reference MEF 26.2 Section 13.5 ENNI Token Share Service Attribute. | [optional] [default to null]
**envelopes** | [**List**](Envelope.md) |  | [optional] [default to null]
**vuniList** | [**List**](CarrierEthernetVirtualUniRef.md) | Pointer to CarrierEthernetVirtualUnit(s). | [optional] [default to null]
**ovcEndPoint** | [**List**](CarrierEthernetOvcEndPointRef.md) | Pointer to CarrierEthernetOvcEnd-Point(s). | [optional] [default to null]

## 12.6 CarrierEthernetOvcEndPoint Service Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | An identifier for the OVC End Point intended for operating purposes. Reference MEF 26.2 Section 16.1 OVC End Point Identfier Service Attribute. | [optional] [default to null]
**role** | [**OvcEndPointRole**](OvcEndPointRole.md) |  | [optional] [default to null]
**endPointMap** | [**OvcEndPointMap**](OvcEndPointMap.md) |  | [optional] [default to null]
**egressMap** | [**List**](OvcEpEgressMap.md) |  | [optional] [default to null]
**egressEquivalenceClassIdentifier** | [**EecMap**](EecMap.md) |  | [optional] [default to null]
**egressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all egress EI Frames mapped to the OVC End Point Reference MEF 26.2 Section 16.11 Egress Bandwidth Profile per OVC End Point Service Attribute. | [optional] [default to null]
**egressBandwidthProfilePerEec** | [**List**](BandwidthProfilePerEquivalenceClassName.md) | For each EEC Name listed, Bandwidth Profile Flow parameters, for all egress EI Frames mapped to that EEC Name at the OVC End Point. Reference MEF 26.2 Section 16.13 Egress Bandwidth Profile per Egress Equivalence Class Name Service Attribute. | [optional] [default to null]
**aggregationLinkDepth** | [**List**](AggLinkDepth.md) | The number of ENNI links that can carry ENNI Frames for each S-VLAN ID mapped to the OVC End Point.  Reference MEF 26.2 Section 16.14 OVC End Point Aggregation Link Depth Service Attribute. | [optional] [default to null]
**maintenanceIntermediatePoint** | [**String**](string.md) |  | [optional] [default to null]
**maintenanceEndPointList** | [**List**](MepLevelAndDirection.md) | The MEPs enable for the OVC End Point.  Reference MEF 26.2 Section 16.17 OVC End Point Maintenance End Point List Service Attribute. | [optional] [default to null]
**virtualUni** | [**List**](CarrierEthernetVirtualUniRef.md) |  | [optional] [default to null]
**operatorUni** | [**List**](CarrierEthernetOperatorUniRef.md) |  | [optional] [default to null]
**enniService** | [**List**](CarrierEthernetEnniServiceRef.md) |  | [optional] [default to null]
**ovc** | [**CarrierEthernetOvcRef**](CarrierEthernetOvcRef.md) |  | [optional] [default to null]
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**ingressClassOfServiceMap** | [**CosMap**](CosMap.md) |  | [optional] [default to null]
**colorMap** | [**ColorIdentifier**](ColorIdentifier.md) |  | [optional] [default to null]
**ingressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all ingress EI Frames mapped to the OVC End Point or EVC End Point. Reference MEF 26.2 Section 16.10 Ingress Band-width Profile per OVC End Point Service Attribute. Reference MEF 10.4 Section 10.8 EVC EP Ingress Bandwidth Profile Service Attribute. The absence of this attribute corresponds to a Service Attrib-ute of None. | [optional] [default to null]
**ingressBandwidthProfilePerCosName** | [**List**](BandwidthProfilePerClassOfServiceName.md) | For each CoS Name listed, Bandwidth Profile Flow parameters for all ingress EI Frames mapped to that CoS Name at the EVC End Point or OVC End Point. Reference MEF 26.2 Section 16.12 Ingress Bandwidth Profile per Class of Service Name Service and MEF 10.4 Section 10.9 EVC EP Class of Service Name Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**sourceMacAddressLimit** | [**List**](SourceMacAddressLimit.md) | Specifies a limit on the number of differ-ent Source MAC address for which in-gress EI Frames at this EVC End Point or OVC End Point will be delivered. The absence of this attribute corresponds to a Service Attribute value of None. Refer-ence MEF 10.4 Section 10.12 EVC EP Source MAC Address Limit Service At-tribute and MEF 26.2 Section 16.15 OVC End Point Source MAC Address Limit Service Attribute. | [optional] [default to null]

## 12.7 CarrierEthernetOvcEndPointRef Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ovcRef** | [**CarrierEthernetOvcRef**](CarrierEthernetOvcRef.md) |  | [optional] [default to null]
**id** | [**UUID**](UUID.md) | Points to CarrierEthernetOvcEndPoint | [optional] [default to null]

## 12.8 CarrierEthernetOvc Service Attributes

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | An identifier for the OVC intended for managment purposes. Reference MEF 26.2 Section 12.1 OVC Identifier Service Attribute. | [optional] [default to null]
**ovcType** | [**ConnectionType**](ConnectionType.md) |  | [optional] [default to null]
**endPointList** | [**List**](CarrierEthernetOvcEndPoint.md) | A list of OVC End Points associated by the OVC. Reference MEF 26.2 Section 12.3 OVC End Point List Service Attribute. | [optional] [default to null]
**maximumNumberOfUniOvcEndPoints** | [**Integer**](integer.md) | The bound on the number of OVC End Points at different UNIs that can be associated by the OVC. Reference MEF 26.2 Section 12.4 Maximum Number of UNI OVC End Points Service Attribute. | [optional] [default to null]
**maximumNumberOfEnniOvcEndPoints** | [**Integer**](integer.md) | The bound on the number of OVC End Points at ENNIs that can be associated by the OVC. | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | This attributes denotes the maximum frame size in bytes. For EVC it is &gt;&#x3D;1522. For OVC it is &gt;&#x3D;1526. | [optional] [default to null]
**ovcCeVlanIdPreservation** | [**VlanIdPreservation**](VlanIdPreservation.md) |  | [optional] [default to null]
**ovcCeVlanPcpPreservation** | [**String**](string.md) |  | [optional] [default to null]
**ovcCeVlanDeiPreservation** | [**String**](string.md) |  | [optional] [default to null]
**ovcSvlanPcpPreservation** | [**String**](string.md) |  | [optional] [default to null]
**ovcSvlanDeiPreservation** | [**String**](string.md) |  | [optional] [default to null]
**listOfClassOfServiceNames** | [**List**](string.md) | A list of Class of Service Names. Reference MEF 26.2 Section 12.12 OVC List of Class of Service Names Service Attribute. | [optional] [default to null]
**frameDelivery** | [**FrameDisposition**](FrameDisposition.md) |  | [optional] [default to null]
**ovcL2cpAddressSet** | [**L2cpAddressSet**](L2cpAddressSet.md) |  | [optional] [default to null]
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**cTagPcpPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the PCP field in the C-Tag in Ingress EI Frames is preserved when the Egress EI Frame also has a C-Tag. Reference MEF 26.2 Section 12.8 OVC CE-VLAN PCP Preservation Service Attribute and MEF 10.4 Section 8.5 EVC C-Tag PCP Preservation Service Attribute. | [optional] [default to null]
**cTagDeiPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the DEI field in the C-Tag in Ingress Frames is preserved when the Egress EI Frame also has C-Tag. Reference MEF 26.2 Section 12.9 OVC CE-VLAN ID DEI Preservation Service Attribute and MEF 10.4 Section 8.6 EVC C-Tag DEI Preservation Service Attribute. | [optional] [default to null]
**connectionType** | [**ConnectionType**](ConnectionType.md) |  | [optional] [default to null]
**frameDisposition** | [**FrameDisposition**](FrameDisposition.md) |  | [optional] [default to null]
**listOfCosNames** | [**List**](string.md) | Used to specify all the Class of Service Names supported by an EVC or OVC. Reference MEF 10.4 Section 8.7 EVC List of Class of Service Names Service Attribute. The Class of Service Names supported by the OVC. Reference MEF 26.2 Section 12.12 OVC List of Class of Service Names Service Attribute. | [optional] [default to null]
**availableMegLevel** | [**List**](MegLevel.md) | The lowest MEG level for which SOAM Frames are not peered or discarded by the SP or Operator. If this attribute is not present there is no such level (that is, SOAM frames are all MEG levels may be peered or discarded by the SP or Opera-tor). Reference MEF 10.4 Section 8.11 EVC Available MEG Level Service Attribute and MEF 26.2 Section 12.15 OVC Available MEF Level Service Attribute. | [optional] [default to null]
**carrierEthernetSls** | [**List**](carrierEthernetSls.md) | Technical details of the service level in terms of Performance Objectives, agreed between the Service Provider and the Subscriber or between Service Provider and the Operator as part of the Service Level Agreement. A given SLS might contain 0,1 or more Performance Objec-tives for each Performance Metric.  Ref-erence MEF 10.4 Section 8.8 EVC Ser-vice Level Specification Service Attribute and MEF 26.2 Section 12.13 OVC Service Level Specification Service Attribute. | [optional] [default to null]

## 12.9 CarrierEthernetOvcRef Attributes 

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**href** | [**URI**](URI.md) |  | [optional] [default to null]
**id** | [**UUID**](UUID.md) |  | [optional] [default to null]

<p style="page-break-before:always;"></p>

# 13. Common Resources

This section details the data types and enumerations that are used by muliple resources and therefore supported in a common area.

## 13.1 AdminState

This enumeration is for Administrative states. Refer to ITU-T X.731.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**state** | [**String**](string.md) |  | [optional] [default to null]

## 13.2 AggLinkDepth

This is a pair of <VLAN ID, link depth> indicating that a given VLAN ID maps to a given num-ber of links in the Port Conversation ID to Aggregation Link Map.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**linkDepth** | [**Integer**](integer.md) | The number of links for the aggregation link. | [optional] [default to null]
**vlanId** | [**VlanId**](VlanId.md) |  | [optional] [default to null]

## 13.3 AvailableMegLevel

This enumeration is for available MEG level, with value 0-7. NONE indicates that SOAM EI Frames are not guaranteed to pass over at any MEF level. Reference MEF 10.4 Section 8.11 EVC Available MEG Level and MEF 26.2 Section 12.15 OVC Available MEG Level Service Attribute.
Contains Enumeration Literals:

## 13.4 BwpFlow

The BwpFlow object class represents the Bandwidth Profile Flow which includes the bandwidth profile parameters such as CIR, CIRmax, EIR, EIRmax, CBS, EBS, Coupling Flag, Color Mode, etc. The BwpFlow is associated with one of CarrierEthernetOperatorUni, CarrierEthernetSub-scriberUni, CarrierEthernetVuni, CosIdentifier, EecIdentifier; and with Envelope. Reference MEF 10.4 Section 12 Bandwidth Profiles and MEF 26.2 Section 17 Bandwidth Profiles.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cir** | [**Integer**](integer.md) | Attribute represents Committed Information Rate. When added to unused committed bandwidth provided from higher-ranked Bandwidth Profile Flows (depending on the value of CF for the higher-ranked Bandwidth Profile Flows), limits the average rate in bits per second at which Service Frames for this Bandwidth Profile Flow can be declared Green. | [optional] [default to null]
**cirMax** | [**Integer**](integer.md) | Attribute represents Maximum Committed Information Rate. Limits the average rate in bits per second at which Service Frames for this Bandwidth Profile Flow can be declared Green (regardless of unused committed bandwidth from higher ranked Bandwidth Profile Flows). | [optional] [default to null]
**cbs** | [**Integer**](integer.md) | Attribute represents Committed Burst Size. Limits by how much, and for how long, the amount of traffic declared Green for this Bandwidth Profile Flow in the short term can exceed the committed bandwidth made available to this Band-width Profile Flow over the long term in bytes. | [optional] [default to null]
**eir** | [**Integer**](integer.md) | Attribute represents Excess Information Rate. When added to unused excess bandwidth from higher-ranked Bandwidth Profile Flows, and to un- used committed bandwidth* (depending on the value of CF for this Bandwidth Profile Flow and CF0 for the Envelope), limits the average rate in bits per second at which Service Frames for this Bandwidth Pro- file Flow can be declared Yellow.  | [optional] [default to null]
**eirMax** | [**Integer**](integer.md) | Attribute represents Maximum Excess Information Rate. Limits the average rate in bits per second at which Service Frames for this Bandwidth Profile Flow can be declared Yellow (regardless of unused excess bandwidth from higher-ranked Bandwidth Profile Flows or unused committed bandwidth). | [optional] [default to null]
**ebs** | [**Integer**](integer.md) | Attribute represents Excess Burst Size. Limits by how much, and for how long, the amount of traffic declared Yellow for this Bandwidth Profile Flow in the short term can exceed the excess band- width made available to this Bandwidth Profile Flow over the long term. | [optional] [default to null]
**couplingFlag** | [**Boolean**](boolean.md) | Attribute represents coupling flag. Determines whether unused committed bandwidth for this Bandwidth Profile Flow is made available as excess bandwidth for this Bandwidth Profile Flow or as commit-ted bandwidth for the next lower-ranked Bandwidth Profile Flow. 0/FALSE means overflow green tokens are used as green tokens in the next lowest BWP Flow in the Envelope. 1/TRUE means they are used as yellow tokens for this BWP Flow. | [optional] [default to null]
**colorMode** | [**ColorMode**](ColorMode.md) | Attribute represents color mode. Indicates whether Service Frames for this Band-width Profile Flow that are identified as Yellow on input to the Bandwidth Profile Algorithm can be declared Green or not.  | [optional] [default to null]
**envelopeId** | [**String**](string.md) | This attribute identifies the Envelope that the Bandwidth Profile belongs to. | [optional] [default to null]
**envelopeRank** | [**Integer**](integer.md) | This attribute denotes the rank of the bandwidth profile flow in the envelope. | [optional] [default to null]
**tokenRequestOffset** | [**Integer**](integer.md) | Attribute represents Token Request Off-set. Adjusts the bandwidth consumed by each Service Frame in the Bandwidth Profile Flow relative to the length of the Service Frame. | [optional] [default to null]

## 13.5 ConnectionType

This enumeration indicates the roles of OVC/EVC Endpoints associated with OVC/EVC. Point-to-Point, Multipoint-to-Multipoint, or Rooted-Multipoint. Reference MEF 10.4 Section 8.3 EVC Type Service Attribute and MEF 26.2 Section 12.2 OVC Type Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.6 ConversationIdToAggregationLinkMap

This is a Port Conversation ID to Aggregation Link Map as defined in IEEE Std 802.1AX-2014. Reference MEF 10.4 Section 9.6 Subscriber UNI Port Conversation ID to Aggregation Link Map Service Attribute and MEF 26.2 Section 9.6 ENNI Port Conversation ID to Aggregation Link Map Common Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**conversationId** | [**List**](integer.md) |  | [optional] [default to null]
**linkNumberIdList** | [**List**](integer.md) | The link number ID of the aggregation link. | [optional] [default to null]

## 13.7 ColorFieldType

This enumeration is for selecting which frame field being used for color indication.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | [**String**](string.md) |  | [optional] [default to null]

## 13.8 ColorIdentifier

Represents the Color Identifier. The Color Identifier is a pair of the form <F,M> where F is a field in the ingress EI Frame and M is a mapping between each possible value of the field F and a Color.  The ColorIdentifier object class is associated with CarrierEthernetServiceEndPoint (EvcEndPoint or OvcEndPoint), in addition to the different field F, such as SepColorIdPac, PcpColorIdPac, Dei-ColorIdPac and DscpColorIdPac.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**colorFieldType** | [**ColorFieldType**](ColorFieldType.md) |  | [optional] [default to null]
**deiColorPac** | [**List**](object.md) | This attribute represents the relationship between the ColorIdentifier and the DeiColorIdPac (representing the choice that maps VLAN Tag DEI to Color). | [optional] [default to null]
**pcpColorPac** | [**List**](PcpColorIdPac.md) | This attribute represents the relationship between the ColorIdentifier and the PcpColorIdPac (representing the choice that maps VLAN tag PCPs to Color). | [optional] [default to null]
**sepColorPac** | [**List**](SepColorIdPac.md) | This attribute represents the relationship between the ColorIdentifier and theh SepColorIdPac (representing the choice that maps EVC End Point or OVC End Point to Color). | [optional] [default to null]
**dscpColorPac** | [**List**](DscpColorIdPac.md) | This attribute represents the relationship between the ColorIdentifier and theh DscpColorIdPac (representing the choice that maps DSCP values to Color). | [optional] [default to null]

## 13.9 ColorMode

This enumeration indicates whether the Color Identifier of the Service Frame is considered by the Bandwidth Profile Algorithm.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | [**String**](string.md) |  | [optional] [default to null]

## 13.10 CosIdentifier

The CosIdentifier represents the Class of Service Identifier. Each ingress EI Frame mapped to the given EVC/OVC End Point has a single Class of Service.  The Class of Service can be determined from inspection of the content of the ingress EI Frame. It is associated with the SepCosIdPac, or the PcpCosIdPac or the DscpCosIdPac (when the Class of Service Identifier mapping type is Ser-vice End Point or PCP values or DSCP values respectively). EI Frames of L2CP protocols may be identified by a Class of Service Identifier, mapping to specified CoS Name.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cosName** | [**String**](string.md) | This attribute denotes the Class of Service name that the CosIdentifier maps to. | [optional] [default to null]
**l2cpProtocolList** | [**List**](L2cpProtocol.md) | This attribute lists the L2CP protocols that map to the Class of Service name. | [optional] [default to null]
**sepCosIdPac** | [**List**](AnyType.md) | This attribute represents the relationship between the CosName and the SepCosId-Pac when the cosMappingType in Cos-Map is END_POINT and the cosName is not only for L2CP. | [optional] [default to null]
**pcpCosIdPac** | [**List**](PcpCosIdPac.md) | This attribute represents the relationship between the CosName and the PcpCosId-Pac when cosMappingType in CosMap is PCP and the cosName is not only for L2CP. | [optional] [default to null]
**dscpCosIdPac** | [**List**](DscpCosIdPac.md) | This attribute represents the relationship between the CosName and the Dscp-CosIdPac when the cosMappingType in CosMap is DSCP and the cosName is not only for L2CP. | [optional] [default to null]

## 13.11 CosNameAndColorToDeiPac

The CosNameAndColorToDeiPac represents the Egress Map that maps from CoS Name and In-gress Color to DEI. Reference MEF 26.2 Section 16.8.2 OVC End Point Egress Map Service At-tribute Form CC->S-Tag DEI and Section 16.8.5 OVC End Point Egress Map Form CC->C-Tag DEI.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ingressCosName** | [**String**](string.md) |  | [optional] [default to null]
**ingressColor** | [**FrameColor**](FrameColor.md) |  | [optional] [default to null]
**deiValue** | [**DeiOrDiscard**](DeiOrDiscard.md) |  | [optional] [default to null]

## 13.12 CosNameAndColorToPcpPac

The CosNameAndColorToPcpPac represents the Egress Map that maps from CoS Name and In-gress Color to PCP. Reference MEF 26.2 Section 16.8.3 OVC End Point Egress Map Service At-tribute Form CC->S-Tag PCP and 16.8.6 OVC End Point Egress Map Form CC->C-Tag PCP.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ingressCosName** | [**String**](string.md) |  | [optional] [default to null]
**ingressColor** | [**FrameColor**](FrameColor.md) |  | [optional] [default to null]
**pcpValue** | [**PcpOrDiscard**](PcpOrDiscard.md) |  | [optional] [default to null]

## 13.13 CosNameToPcpPac

The CosNameToPcpPac represents the Egress Map that maps from CoS Name to PCP. Reference MEF 26.2 Section 16.8.1 OVC End Point Egress Map Service Attribute Form CN->S-Tag PCP and Section 16.8.4 OVC End Point Egress Map Form CN->C-Tag PCP.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ingressCosName** | [**String**](string.md) |  | [optional] [default to null]
**pcpValue** | [**PcpOrDiscard**](PcpOrDiscard.md) |  | [optional] [default to null]

## 13.14 DeiColorIdPac

This represents the Color Identifier that maps the VLAN Tag (S-Tag or C-Tag) DEI value to Col-or, DEI=0 for Green color and DEI=1 for Yellow color. For an EVC End Point or OVC End Point at UNI or in a VUNI, the DEI value is from C-Tag Ingress EI frames. For an OVC End Point at an ENNI and not in a VUNI, the DEI value is from S-Tag or the ingress EI frames.

## 13.15 DeiOrDiscard

This enumeration lists the DEI value for color or discard and is used for Egress Map.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | [**String**](string.md) |  | [optional] [default to null]

## 13.16 DscpColorIdPac

This represents the Color Identifier that maps DSCP (IPv4 or IPv6) values to Color.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ipVersion** | [**IpVersion**](IpVersion.md) | This attribute denotes which IP version is used. It can be IPV4, IPV6 or IPV4 and IPV6. | [optional] [default to null]
**dscpValueForGreenList** | [**List**](integer.md) |  | [optional] [default to null]
**dscpValueForYellowList** | [**List**](integer.md) |  | [optional] [default to null]

## 13.17 DscpEecIdPac

This represents the Egress Equivalence Class Identifier that maps the IP DSCP values to Egress Equivalence Class Name(s).  It can map a list of DSCP values to two different Egress Equivalence Class Names, one for ingress EI frames carrying IPv4 packets and a different one for ingress EI frames carrying IPv6 packet.  It also can map a list of DSCP values (both IPv4 and IPv6 packets) to an Egress Equivalence Class Name.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ipVersion** | [**IpVersion**](IpVersion.md) | This attribute denotes which IP version is used. It can be IPV4, IPV6 or IPV4 and IPV6. | [optional] [default to null]
**dscpValueList** | [**List**](DscpValue.md) | This attribute is a list of DSCP values that maps to the EEC Name.  If NO_IP_PACKET is included here, the ipVersion must be IPV4_AND-IPV6. | [optional] [default to null]

## 13.18 EecIdentifier

The EecIdentifier represents the Egress Equivalence Class Identifier. Each egress EI Frame mapped to the given EVC/OVC End Point has a single Egress Equivalence Class. The Egress Equivalence Class can be determined from inspection of the content of the egress EI Frame. It is associated with the SepCosIdPac, or the PcpCosIdPac, or the DscpCosIdPac (representing mapping to EVC/OVC End Point, or PCP, or DSCP respectively). EI Frames of L2CP protocols may be identified by an Egress Equivalence Class Identifier, mapping to specific Egress Equivalence Class Name.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**eecName** | [**String**](string.md) | This attribute denotes the Egress Equiva-lence Class Name that the EecIdentifier maps to. | [optional] [default to null]
**l2cpProtocolList** | [**List**](L2cpProtocol.md) | This attribute lists the L2CP protocols that map to the Egress Equivalence Class Name. | [optional] [default to null]
**pcpEecIdPac** | [**List**](PcpEecIdPac.md) | This attribute represents the relationship between the EecIdentifier and a PcpEecIdPac if the eecMappingType in EecMap is PCP and the eecName is not only for L2CP. | [optional] [default to null]
**dscpEecIdPac** | [**List**](DscpEecIdPac.md) | This attribute represents the relationship between the EecIdentifier and a DscpEecIdPac if the eecMappingType in EecMap is DSCP and the eecName is not only for L2CP. | [optional] [default to null]

## 13.19 Envelope

This represents the UNI or ENNI Envelopes service attribute.  Each Envelope consists of an Enve-lope ID and Envelope Coupling Flag. Defined in MEF-Common. Reference MEF 10.4 Section 12.1.1 Envelope Parameters and MEF 26.2 Section 17.1.1 Envelope Parameters.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**envelopeId** | [**String**](string.md) | The attribute is a string that identifies the Envelope. | [optional] [default to null]
**couplingFlagForIndexZero** | [**Boolean**](boolean.md) | This attribute denotes the coupling flag for index zero. FALSE for 0 (overflow Green tokens are discarded) and TRUE for 1 (overflow Green tokens can be used as Yellow tokens). | [optional] [default to null]

## 13.20 EthernetFrameFormat

This is a single value read only attribute. Reference MEF 10.4 Section 9.7 Subscriber UNI Service Frame Format Service Attribute and MEF 26.2 Section 14.7 Operator UNI Service Frame Format Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | [**String**](string.md) |  | [optional] [default to null]

## 13.21 EvcEpEgressMap

Represents the Egress that is a set of mappings that determine the content of the C-Tag of an egress EI Frame.  It is associated with EVC End Point. Reference MEF 10.4 Section 10.7 EVC End Point Egress Map Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cosName** | [**String**](string.md) | The CoS Name assigned to the Service Frame at the ingress UNI. | [optional] [default to null]
**color** | [**FrameColor**](FrameColor.md) | The Color assigned to the Service Frame at the ingress UNI. | [optional] [default to null]
**pcp** | [**PcpOrDiscard**](PcpOrDiscard.md) | The PCP value to set in the C-tag of the egress Service Frame. | [optional] [default to null]
**dei** | [**DeiOrDiscard**](DeiOrDiscard.md) | The DEI value to set in the C-tag of the egress Service Frame. | [optional] [default to null]

## 13.22 EvcEpEgressMapType

This lists the EVC End Point Egress Map types, either CoS Name and Ingress Color to PCP, or CoS Name and Ingress Color to DEI. Reference MEF 10.4 Section 10.7 EVC End Point Egress Map Service Attribute.

## 13.23 EvcEndPointRole

This enumeration is indicating how external interface frames mapped to the EVC End Point can be forwarded:

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.24 FrameColor

This enumeration lists the Frame Color of either Green or Yellow.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.25 FrameDelivery

This enumeration defined MEF 10.3. When the value is conditionally, the specific condition must be addressed by the users.  What conditions should be supported are not in the scope.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.26 Identifier45

Data type attribute unique by network administrative domain, containing no more than 45 charac-ters and non-null RFC Display String but not contain the characters 0x00 through 0x1F.

## 13.27 IpVersion

This enumeration lists the IP versions, including IPv4, IPv6 and both.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.28 L2cpAddressSet

Enumeration listing the L2CP Address Set. Reference MEF 45.1 Section 8.1 L2CP Address Set Service Attribute.
Contains Enumeration Literals:

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**bridgedAddresses** | [**String**](string.md) | CTA - CEVLAN Tag Aware for VLAN-based services where the CE-VLAN ID is used to map a frame to a service. CTB - CVLAN Tag Blind for Port-based services where the CE-VLAN ID not used to map a frame to a service. CTB2 -  CVLAN Tag Blind Option 2 for point-to-point Port-based services that support the EPL Option 2 L2CP processing. | [optional] [default to null]

## 13.29 L2cpPeering

This is a list that specifies the L2CP Protocol Identifier and the Destination Address in use by the protocol entity. Reference MEF 45.1 Section 8.2 L2CP Peering Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**protocolId** | [**L2cpProtocol**](L2cpProtocol.md) | Protocol ID for which frames will be peered. | [optional] [default to null]
**destinationAddress** | [**String**](string.md) | Destination address for which frames will be peered. | [optional] [default to null]
**linkIdList** | [**List**](string.md) | Identifiers for the links on which the specified protocol will be peered.  If no links are specified the protocol is peered on all links. | [optional] [default to null]

## 13.30 L2cpProtocol

This datatype defines a L2CP protocol (LLC address type or EtherType) with possible subtype. Reference MEF 45.1 Section 8.2 L2CP Peering Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**l2cpProtocolType** | [**L2cpProtocolType**](L2cpProtocolType.md) |  | [optional] [default to null]
**llcAddressOrEtherType** | [**Integer**](integer.md) |  | [optional] [default to null]
**subType** | [**List**](integer.md) |  | [optional] [default to null]

## 13.31 L2cpProtocolType

This lists the L2CP protocol types, either EtherType or LLC Address. Reference MEF 45.1 Section 8.2 L2CP Peering Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**vlanType** | [**String**](string.md) |  | [optional] [default to null]

## 13.32 MepDirection

This lists the enumerations for MEP direction.
Contains Enumeration Literals:

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.33 MepLevelAndDirection

This datatype defines the MEG Level and MEP direction.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**mepDirection** | [**MepDirection**](MepDirection.md) |  | [optional] [default to null]
**level** | [**Integer**](integer.md) |  | [optional] [default to null]

## 13.34 OperationalState

This enumeration is for Operational states. Refer to ITU-T X.731.
Contains Enumeration Literals:

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**state** | [**String**](string.md) |  | [optional] [default to null]

## 13.35 OvcEndPointRole

This enumeration is indicating how external interface frames mapped to the OVC End Point can be forwarded:

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.36 OvcEpEgressMap

Represents the Egress that is a set of mappings that determine the content of the S-Tag or C-Tag of an egress EI Frame.  It is associated with OVC End Point. Reference MEF 26.2 Section 16.8 OVC End Point Egress Map Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**egressMapType** | [**OvcEgressMapType**](OvcEgressMapType.md) | This attribute determines which form to take to apply frame color indication, among CoS name and Ingress Color to C-Tag PCP, or CoS name and Ingress Color to S-Tag PCP, or CoS Name and Ingress Color to C-Tag DEI, or CoS Name to C-Tag PCP or CoS Name to S-Tag PCP. | [optional] [default to null]
**cosNameAndColorToDeiPacList** | [**List**](CosNameAndColorToDeiPac.md) | This attribute represents the relationship between the EgressMap and the CosNameAndColorToDeiPac (representing the attribute set for using CoS Name and ingress color to egress DEI mapping). | [optional] [default to null]
**cosNameToPcpPacList** | [**List**](CosNameToPcpPac.md) | This attribute represents the Egress Map that maps from CoS name to PCP. | [optional] [default to null]
**cosNameAndColorToPcpPacList** | [**List**](CosNameAndColorToPcpPac.md) | This attribute represents the relation between the EgressMap and the CosNameAndColorToPcpPac (representing the attribute using the CoS Name and ingress color to egress PCP mapping). | [optional] [default to null]

## 13.37 OvcEpEgressMapType

This lists the Egress Map types, either CoS Name to PCP, or CoS Name and Ingress Color to PCP, or CoS Name and Ingress Color to DEI for S-Tag or C-Tag. Reference MEF 26.2 Section 16.8 OVC End Point Egress Map Service Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | [**String**](string.md) |  | [optional] [default to null]

## 13.38 PcpColorIdPac

Represents Color Identifier that maps VLAN Tag (S-Tag or C-Tag) PCP values to Color. For an EVC End Point or OVC End Point at UNI or in a VUNI, the PCP values are from C-Tag ingress EI frames.  For an OVC End Point at an ENNI and not in a VUNI, the PCP values are from S-Tag of the ingress EI frames.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**pcpValueForGreenList** | [**List**](integer.md) | This attribute provides a list PCP values map to green ingress EI frames.  The pcpValueForGreenList and the pcpValueForYellowList must disjoint and the union of the two lists must include all possible PCP values. | [optional] [default to null]
**pcpValueForYellowList** | [**List**](integer.md) | This attribute provides a list PCP values map to yellow ingress EI frames.  The pcpValueForGreenList and the pcpValueForYellowList must disjoint and the union of the two lists must include all possible PCP values. | [optional] [default to null]

## 13.39 PcpEecIdPac

This represents the Egress Equivalence Class Identifier that maps a list of PCP values to Egress Equivalence Class Name.  For an EVC End Point or an OVC End Point at UNI or in a VUNI, the PCP values are from C-Tag egress EI frames.  For an OVC End Point at an ENNI and not in a VUNI, the PCP values are from S-Tag of the egress EI frames.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**pcpValueList** | [**List**](PcpOrUntagged.md) | This attribute provides a list of PCP values that map to Egress Equivalence Class Name. | [optional] [default to null]

## 13.40 PcpOrDiscard

This enumeration lists the one of PCP values or DISCARD.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | [**String**](string.md) |  | [optional] [default to null]

## 13.41 PhysicalLayer

This enumeration lists IEEE802.3 (2012) defined list excluding 1000BASE-PX-D and 1000BASE-PX-U. NONE is added with further MEF 10.3 discussion, for supporting logical in-terfaces.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.42 PositiveInteger

Data type with single attribute, positiveint, which is an Integer > 0.

## 13.43 SepColorIdPac

Represents the Color Identifier that maps to the EVC End Point or the OVC End Point to Color.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**color** | [**FrameColor**](FrameColor.md) | This attribute denotes the color of the EI frame, green or yello. | [optional] [default to null]

## 13.44 SepEecIdPac

This represents the Egress Equivalence Class Identifier that maps the EVC End Point or OVC End Point to an Egress Equivalence Class Name.

## 13.45 SourceMacAddressLimit

This limits the number of source MAC addresses that can be used in ingress external interface frame mapped to the End Point of all types over a time interval.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | [**Integer**](integer.md) | This attribute denotes the maximum acceptable source MAC addresses. | [optional] [default to null]
**interval** | [**Integer**](integer.md) | This attribute denotes the time interval in milliseconds. | [optional] [default to null]

## 13.46 SyncModePerLink

A link may consist of one or more physical ports.  This data type includes the link ID and sync mode of the physical port associated to the link id.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**syncModeEnabled** | [**Boolean**](boolean.md) | This attribute denotes whether the Synchronous Mode is enabled on the link with the Link ID. | [optional] [default to null]

## 13.47 TaggedL2cpProcessing

Enumeration representing either 802.1 compliant or not compliant. Reference MEF 45.1 Section 8.3 ENNI Tagged L2CP Frame Processing Multilateral Attribute.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | [**String**](string.md) |  | [optional] [default to null]

## 13.48 TimeIntervalT

Time interval T for PM. E.g., 1 month, 20 days, 2 weeks.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**number** | [**Integer**](integer.md) | This denotes the value (for the unit). | [optional] [default to null]
**unit** | [**String**](string.md) | Time interval unit. | [optional] [default to null]

## 13.49 TimeAndDate

Data type defined for Time and Date in UTC.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**day** | [**Integer**](integer.md) | Denotes the day. | [optional] [default to null]
**hour** | [**Integer**](integer.md) | Denotes the hour. | [optional] [default to null]
**minute** | [**Integer**](integer.md) | Denotes the minute. | [optional] [default to null]
**month** | [**Integer**](integer.md) | Denotes the month. | [optional] [default to null]
**second** | [**Integer**](integer.md) | Denotes the second. | [optional] [default to null]
**year** | [**Integer**](integer.md) | Denotes the year. | [optional] [default to null]

## 13.50 TimeIntervalUnit

This enumeration represents time interval unit, e.g., month, day, week, hour, etc. Contains Enumeration Literals.

## 13.51 VlanId

Data type with single attribute, vlanId which is defined as a PostiveInteger. Value 1 to 4094.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**vlanId** | [**Integer**](integer.md) |  | [optional] [default to null]

## 13.52 VlanIdListing

The list VLAN IDs, either when type=LIST, or when type=EXCEPT (which means the VLAN IDs except the listed).  When type=ALL, the VLAN ID list is not applicable.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | [**VlanIdMappingType**](VlanIdMappingType.md) |  | [optional] [default to null]
**vlanIdList** | [**List**](VlanId.md) | This is a list of VLAN IDs. | [optional] [default to null]

## 13.53 VlanIdListOrUntag

VLAN ID types, ALL for all VLAN IDs, LIST for a list of VLAN IDs, EXCEPT for all VLAN IDs except the listed, UNTAGGED to indicate that untagged and priority-tagged frames are mapped to this end point.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | [**VlanIdMappingTypeOrUntag**](VlanIdMappingTypeOrUntag.md) |  | [optional] [default to null]
**vlanIdList** | [**List**](VlanId.md) |  | [optional] [default to null]

## 13.54 VlanIdMappingType

Enumeration for VLAN ID types, ALL for all VLAN IDs, LIST for a list of VLAN IDs, EX-CEPT for all VLAN IDs except the listed.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.55 VlanIdMappingTypeOrUntag

Enumeration for VLAN ID types, ALL for all VLAN IDs, LIST for a list of VLAN IDs, EX-CEPT for all VLAN IDs except the listed, UNTAGGED to indicate untagged and priority-ragged frames are mapped to this end point.

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

## 13.56 VlanIdPreservation

Enumeration for VLAN ID Preservation:

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
<p style="page-break-before:always;"></p>

# 14. Legato Service Order for Carrier Ethernet Services

The following section details how the two components of the Legato API are associated from an implementation perspective.  Specifically discussed are the binding between the Envelope and Payload.

## 14.1 Legato Envelope and MEF Payload Association

The following section provides the developer with a guide on how to associate the envelope part of the Legato API with the Carrier Ethernet payload. A sequence diagram illustrating the pseudo steps needed to create payload, associate to envelope and POST request.

The Legato Envelope and Payload are associated with the Order and specifically OrderItem.  The Envelope OrderItem is associated with a Payload resource such as CarrierEthernetSubscriberUni.

The figure below illustrates the sequencing of coding operations used in building the Legato Envelope and associated set of Carrier Ethernet specific Order Items.  Once the Order is complete it is communicate to the server-side (SOF) with a POST message.

<center>
<img src="media/provisioning.png" alt="prov"  />
</center>

# 15. References

IEEE Std 802.1AX-2014, *Link Aggregation*, December 2014

IEEE Std 802.3-2012, *IEEE Standard for Ethernet*, August 2012

[MEF 4](https://wiki.mef.net/display/CESG/MEF+4+-+MEN+Architecture+Framework), *Metro Ethernet Network Architecture - Part 1: Generic Framework*, May 2004

[MEF 6.3](https://wiki.mef.net/display/CESG/MEF+6.3+-+EVC+Ethernet+Services+Definitions), *Subscriber Ethernet Services Definitions*, November 2019

[MEF 7.4], *Carrier Ethernet Services Information Model*, under development

[MEF 10.4](https://wiki.mef.net/display/CESG/MEF+10.4+-+Subscriber+Ethernet+Service+Attributes), *Subscriber Ethernet Service Attributes*, December 2018

[MEF 26.2](https://wiki.mef.net/display/CESG/MEF+26.2+-+ENNI), *External Network Network Interfaces (ENNI) and Operator Service Attributes*, August 2016

[MEF 45.1](https://wiki.mef.net/display/CESG/MEF+45.1+-+Layer+2+Control+Protocols+in+Ethernet+Services), *Layer 2 Control Protocols in Ethernet Services*, December 2018

[MEF 55](https://wiki.mef.net/display/CESG/MEF+55+-+LSO+Reference+Architecture), *Lifecycle Service Orchestration (LSO): Reference Architecture and Framework*, March 2016
