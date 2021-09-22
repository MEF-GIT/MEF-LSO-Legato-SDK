# MEF-LSO-Legato-SDK Billie Release

## Download Link

Download the entire repository by clicking [here](https://github.com/MEF-GIT/MEF-LSO-Legato-SDK/releases/download/billie-final/MEF-LSO-Legato-SDK-billie.zip)

## Overview

This repository contains the Billie release of the Legato SDK. The SDK includes APIs for Service Catalog, Service Order, Service Inventory and Service Notification functions of the Service Orchestration Functionality (SOF) at the LSO Legato Interface Reference Point (IRP) as defined in the MEF LSO Reference Architecture.

This version updates the payload schemas for:

- Carrier Ethernet (based on MEF 7.4),
- SD-WAN (based on MEF 82) and
- L1CS (based on MEF 111).

**NOTE:** Some parts of the release are for MEF Members only, such as the draft, in-progress versions of the API Developer Guides for each of the service types listed above.

## Scope

It includes API definitions for the following functional areas:

- Service Catalog - This includes support for
  - Service Specification - Retrieve operations only
  - Not in scope
    - Service Specifications - Create, Amend/Modify, Delete operations
    - Service Catalog, Service Category, Service Candidate, Job/Task
- Service Ordering - This includes support for
  - Service Order/OrderItem - Create, Retrieve operations only
  - Not in scope
    - Service Order/OrderItem - Amend/Modify/Cancel, Delete operations
- Service Inventory - This includes support for
  - Service - Retrieve operations only
  - Not in scope
    - Service - Create, Amend/Modify, Delete operations
- Service Notification - This includes support for
  - Hub - Create, Delete, Retrieve operations
  - Service Specification - Create, Delete, StateChange event notifications
  - Service Order/OrderItem - Create, StateChange event notifications
  - Service events - Create, Delete, StateChange event notifications
  - Not in scope
    - Hub - Modify operations
    - Retrieve Notification records history/log
    - AttributeValueChange event notifications

In addition to the Service Provisioning APIs, the SDK includes the following MEF Service Specification schemas:

- SD-WAN Services
- Carrier Ethernet Services
- L1 Connectivity Services

The MEF LSO Legato SDK is released under the Apache 2.0 license.

More information about the LSO Legato API reference point and it's roadmap can be found here:

https://wiki.mef.net/display/CESG/LSO+Legato

## Maturity Level

The API files contained in this SDK are evolving and subject to change. They are based on documents that are either work in progress or draft standards that have not yet completed the review cycles and approvals necessary to achieve the status as a MEF standard. MEF is making these publicly available at this time to invite wider industry review.

There is currently [LSO Legato Service Provisioning Project](https://wiki.mef.net/display/LSO/LSO+Legato+Service+API+-+Project+Home+Page) open that aims to  deliver:

- LSO Legato Service Provisioning API (MEF W99)
  - OAS3 API/Schema definitions as YAML files **(DRAFT, part of this SDK release)**
  - API Developer Guide as GFM file **(To be delivered)**
- LSO Legato Service Provisioning Specification - SD-WAN (MEF W100)
  - JSON Schema definitions as YAML files **(DRAFT, part of this SDK release)**
  - Schema Guide as GFM file **(DRAFT, part of this SDK release)**
- LSO Legato Service Provisioning Specification - Carrier Ethernet (MEF W101)
  - JSON Schema definitions as YAML files **(DRAFT, part of this SDK release)**
  - Schema Guide as GFM file **(DRAFT, part of this SDK release)**
- LSO Legato Service Provisioning Specification - L1 (MEF W103)
  - JSON Schema definitions as YAML files **(DRAFT, part of this SDK release)**
  - Schema Guide as GFM file **(DRAFT, part of this SDK release)**

## Contents

This SDK contains the following items:

- `COPYRIGHT` - Copyright 2020 MEF Forum
- `LICENSE` - Contains a copy of the Apache 2.0 license
- `README` - This file
- `serviceApi` - Definitions of the API are found in this directory
  - `catalog` - Contains the API definitions for querying and retrieving _Service-Specification_ instances from the service catalog system in the SOF.
  - `inventory` - Contains the API definitions for querying and retrieving _Service_ instances from the service inventory system in the SOF.
  - `order` - Contains the API definitions for posting _Service-Order_ request to the service order system in the SOF. Each _Service-Order_ contains one or more _Service-Order-Items_, each of which specifies the Service instance (and its characteristics) to be added/updated/deleted.
  - `common` - Contains the API definitions for registering _Notification-Listeners_ to be called-back when the specified condition occurs. Also common API resources and error definition can be found here.
- `serviceSchema` - Contains JSON schema (draft 7) files for
  - SD-WAN Services
  - Carrier Ethernet Services
  - L1 Connectivity Services.
- `documentation` - documentation including API/Schema developer guides and openapi-tools generated API descriptions in markdown format
- `generated\staticBinding` - contains automatically generated (with help of the open source [Sonata Blending Tool](https://github.com/Amartus/SonataBlendingTool)), not normative static bindings of envelope APIs with Service payloads.

## Issues, questions, and Feedback

Issues should be reported with the use of GitHub issues. Questions and feedback should be asked either at [Legato SDK Community](https://github.com/orgs/MEF-GIT/teams/mef-lso-legato-sdk-community) or directly to community_manager@mef.net.

**NOTE:** All artifacts included in this repository have line numbers. When referring to specific content in any of these artifacts, please quote the line numbers to which you are referring.

## Reference Implementations

A reference implementation of the MEF Service Instantiation API may be available from the ONAP EXTAPI project.

https://wiki.onap.org/display/DW/External+API+Framework+Project

## Copyright

© MEF Forum 2021. All Rights Reserved.

## Disclaimer

The information in this publication is freely available for reproduction and use by any recipient and is believed to be accurate as of its publication date. Such information is subject to change without notice and MEF Forum (MEF) is not responsible for any errors. MEF does not assume responsibility to update or correct any information in this publication. No representation or warranty, expressed or implied, is made by MEF concerning the completeness, accuracy, or applicability of any information contained herein and no liability of any kind shall be assumed by MEF as a result of reliance upon such information.

The information contained herein is intended to be used without modification by the recipient or user of this document. MEF is not responsible or liable for any modifications to this document made by any other party.

The receipt or any use of this document or its contents does not in any way create, by implication or otherwise:

(a) any express or implied license or right to or under any patent, copyright, trademark or trade secret rights held or claimed by any MEF member which are or may be associated with the ideas, techniques, concepts or expressions contained herein; nor

(b) any warranty or representation that any MEF member will announce any product(s) and/or service(s) related thereto, or if such announcements are made, that such announced product(s) and/or service(s) embody any or all of the ideas, technologies, or concepts contained herein; nor

(c) any form of relationship between any MEF member and the recipient or user of this document.

Implementation or use of specific MEF standards, specifications, or recommendations will be voluntary, and no Member shall be obliged to implement them by virtue of participation in MEF Forum. MEF is a non-profit international organization to enable the development and worldwide adoption of agile, assured and orchestrated network services. MEF does not, expressly or otherwise, endorse or promote any specific products or services.
