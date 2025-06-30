# MEF W100 Legato SD-WAN Service Schemas and Developer Guide - Fergie Release

## Download Link

Download the entire set of schemas by clicking [here](https://github.com/MEF-GIT/MEF-LSO/tree/sdWan_cfc2_base)

## Introduction

This repository contains the MEF W100 SD-WAN Service Schemas and Developer Guide and corresponding YAML schemas. The work is based on MEF W70.2 SD-WAN Service Attributes and Framework. It includes YAML definitions for the following resources:

- SD-WAN UNI
- SD-WAN VC
- SD-WAN End Point
- Underlay Connectivity UNI
- Underlay Connectivity VC
- Underlay Connectivity End Point

It also provides YAML Schemas for:

- SD-WAN Common resources (includes, but not limited to):
  - Policy
  - Security Policy
  - Application Flows

## High-level release notes

- All resource have been submitted for a Call for Comment Review (Cfc#2) and updated to follow the resources (objects) and associated attributes as defined in MEF W70.2.
- Documents:
  - MEF W100 SD-WAN Service Schemas and Developer Guide v0.2.docx
- YAML Schemas:
  - sdWanCommon.yaml
  - sdWanTypes.yaml
  - sdWanUni.yaml
  - swVc.yaml
  - swVcEndPoint.yaml
  - ucs.yaml
  - ucsEndPoint.yaml
  - ucsUni.yaml

## Maturity Level

The API files contained in this SDK are evolving and subject to change. They are based on documents that are either ratified standards or draft standards that have not yet completed the review cycles and approvals necessary to achieve the status as a MEF standard. MEF is making these publicly available at this time to invite wider industry review.

## Contents

This SDK contains the following items:

- `COPYRIGHT` - Copyright 2023 MEF Forum
- `LICENSE` - Contains a copy of the Apache 2.0 license
- `README` - This file
- `documentation` - All related standards and Developer Guides
- `Service Schema` - Service Specification schemas for:
  - `sdWan` - SD-WAN service Schemas

## Issues, Questions, and Feedback

Issues should be reported with the use of GitHub issues. Questions and feedback should be asked either at [Sonata SDK Community](https://github.com/MEF-GIT/MEF-LSO/tree/sdWan_cfc2_base)or directly to community_manager@mef.net.

**NOTE:** All artifacts included in this repository have line numbers. When referring to specific content in any of these artifacts, please quote the line numbers to which you are referring.

The MEF LSO Sonata SDK is released under the Apache 2.0 license.

## Copyright

© MEF Forum 2023. All Rights Reserved.

## Disclaimer

The information in this publication is freely available for reproduction and use by any recipient and is believed to be accurate as of its publication date. Such information is subject to change without notice and MEF Forum (MEF) is not responsible for any errors. MEF does not assume responsibility to update or correct any information in this publication. No representation or warranty, expressed or implied, is made by MEF concerning the completeness, accuracy, or applicability of any information contained herein and no liability of any kind shall be assumed by MEF as a result of reliance upon such information.

The information contained herein is intended to be used without modification by the recipient or user of this document. MEF is not responsible or liable for any modifications to this document made by any other party.

The receipt or any use of this document or its contents does not in any way create, by implication or otherwise:

(a) any express or implied license or right to or under any patent, copyright, trademark or trade secret rights held or claimed by any MEF member which are or may be associated with the ideas, techniques, concepts or expressions contained herein; nor

(b) any warranty or representation that any MEF member will announce any product(s) and/or service(s) related thereto, or if such announcements are made, that such announced product(s) and/or service(s) embody any or all of the ideas, technologies, or concepts contained herein; nor

(c) any form of relationship between any MEF member and the recipient or user of this document.

Implementation or use of specific MEF standards, specifications, or recommendations will be voluntary, and no Member shall be obliged to implement them by virtue of participation in MEF Forum. MEF is a non-profit international organization to enable the development and worldwide adoption of agile, assured, and orchestrated network services. MEF does not, expressly or otherwise, endorse or promote any specific products or services.