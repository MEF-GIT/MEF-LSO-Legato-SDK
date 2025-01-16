# MEF-LSO-Carrier-Ethernet-Service-Schemas - Call for Comment #4

## Download Link

Download the entire repository by clicking
[here](https://github.com/MEF-GIT/MEF-LSO/tree/develop_ce_service)

## Introduction

This repository contains the MEF LSO Carrier Ethernet Service YAML payload schemas.

It also provides Service Schemas for:

- Subscriber UNI
- Subscriber EVC End Point
- Subscriber EVC
- Operator UNI
- Operator OVC End Point
- Operator OVC
- ENNI
- ENNI Service
- Virtual UNI
- Carrier Ethernet Service Level Specification (SLS)

## Release Irene:

**Readiness status**: Call for Comment #4.

**Summary**:
 
 - MEF W101 document no longer uses the term Legato and moves to term Service. 
 the intention is that these schemas are applicable to mulitple Interface Reference
 Points (Legato, Allegro and Interlude) as well as for internal software systems
 (i.e., SOF).

 - MEF W101 document adds complete set of use cases with JSON and PlantUML JSON diagrams.
 
 - The superclasses (resources) CarrierEthernetExternalInterface, CarrierEthernetServiceEndPoint,
 and CarrierEthernetService are removed.  This is done with the intention to simplify and
 flatten the model.
 
 - The following changes are shown for each Carrier Ethernet supporting YAML file.

 - All resource that have an identifier have added pattern: "[\x20-\x7F]+" and minimum length of 1.

 - All required attributes are removed.

 **carrierEthernetCommon.yaml:**
  - CarrierEthernetExternallInterface, a superclass (resource) removed.
  - CarrierEthernetServiceEndPoint, a superclass (resource) removed.
  - CarrierEthernetService, a superclass (resource) removed.
  - CarrierEthernetUni, an abstract class (resource) removed.
  - AdminState and OperationalState removed. State is handled by the envelope part of API (MEF 99).
  - BwpFlow are seperated to IngressBwpFlow and EgressBwpFlow because all attributes are not shared.
  - BandwidthProfilePerClassOfServiceName are separated to IngressBandwidthProfilePerClassOfServiceName
  and EgressBandwidthProfileClassOfService name because not all attributes are shared.
  - CarrierEthernetPhysicalLink replaces PhysicalLayer.
  
 
 **carrierEthernetEnni.yaml:**
  - CarrierEthernetExternalInterface is not referenced. Therefore attributes are
  are moved into carrierEthernetEnni.yaml.

 **carrierEthernetEnniService.yaml:**
  - CarrierEtherExternalInterface is not referenced. Therefore attributes are
  are moved into carrierEthernetEnniService.yaml.

 **carrierEthernetEvc.yaml:**
  - CarrierEthernetService is not referenced. Therefore attributes are
  are moved into carrierEthernetEvc.yaml.

 **carrierEthernetEvcEndPoint.yaml:**
  - CarrierEthernetServiceEndPoint is not referenced. Therefore attributes are
  are moved into carrierEthernetEvcEndPoint.yaml.

 **carrierEthernetOperatorUni.yaml:**
  - CarrierEthernetUni is not referenced. Therefore attributes are
  are moved into carrierEthernetOperatorUni.yaml.

 **carrierEthernetOvcEndPoint.yaml:**
  - CarrierEthernetServiceEndPoint is not referenced. Therefore attributes are
  are moved into carrierEthernetOvcEndPoint.yaml.

 **carrierEthernetServiceLevelSpecification.yaml:**

 **carrierEthernetSubscriberUni.yaml**
  - CarrierEthernetUni is not referenced. Therefore attributes are
  are moved into carrierEthernetSubscriberUni.yaml.

 **carrierEthernetVirtualUni.yaml**
  - AdminState and OperationalState removed. Therefore attributes are
  are moved into carrierEthernetVirtualUni.yaml.


## Maturity Level

The schema files contained in this repository are evolving and subject to change. They are
based on documents that are either ratified standards or draft standards that
have not yet completed the review cycles and approvals necessary to achieve the
status as a MEF standard. MEF is making these publicly available at this time to
invite wider industry review.


- Subscriber Ethernet Service Attributes:
  - MEF 10.4 - **Published Standard**
- External Network Network Interfaces (ENNI) and Operator Service Attributes
  - MEF 26.2 - **Published Standard**
- Layer 2 Control Protocols in Ethernet Services
  - MEF 45.1 **Published Standard**
- Developer Guide/API:
  - MEF W101 - **work in progress - CfC#4**

## Contents

This repository contains the following items:

- `COPYRIGHT` - Copyright 2024 MEF Forum
- `LICENSE` - Contains a copy of the Apache 2.0 license
- `README` - This file
- `serviceApi` - MEF 99 Service Ordering blended with MEF W101 Carrier Ethernet Payload API
- `documentation` - MEF W101 v0.4 LSO Carrier Ethernet Service Schemas and Developer Guide
- `Postman scripts` - Postman scripts for client testing of MEF 99 with blended MEF W101.

## Issues, Questions, and Feedback

Issues should be reported with the use of GitHub issues. Questions and feedback
should be asked either at


## Copyright

© MEF Forum 2024. All Rights Reserved.

## Disclaimer

The information in this publication is freely available for reproduction and use
by any recipient and is believed to be accurate as of its publication date. Such
information is subject to change without notice and MEF Forum (MEF) is not
responsible for any errors. MEF does not assume responsibility to update or
correct any information in this publication. No representation or warranty,
expressed or implied, is made by MEF concerning the completeness, accuracy, or
applicability of any information contained herein and no liability of any kind
shall be assumed by MEF as a result of reliance upon such information.

The information contained herein is intended to be used without modification by
the recipient or user of this document. MEF is not responsible or liable for any
modifications to this document made by any other party.

The receipt or any use of this document or its contents does not in any way
create, by implication or otherwise:

(a) any express or implied license or right to or under any patent, copyright,
trademark or trade secret rights held or claimed by any MEF member which are or
may be associated with the ideas, techniques, concepts or expressions contained
herein; nor

(b) any warranty or representation that any MEF member will announce any
product(s) and/or service(s) related thereto, or if such announcements are made,
that such announced product(s) and/or service(s) embody any or all of the ideas,
technologies, or concepts contained herein; nor

(c) any form of relationship between any MEF member and the recipient or user of
this document.

Implementation or use of specific MEF standards, specifications, or
recommendations will be voluntary, and no Member shall be obliged to implement
them by virtue of participation in MEF Forum. MEF is a non-profit international
organization to enable the development and worldwide adoption of agile, assured,
and orchestrated network services. MEF does not, expressly or otherwise, endorse
or promote any specific products or services.
