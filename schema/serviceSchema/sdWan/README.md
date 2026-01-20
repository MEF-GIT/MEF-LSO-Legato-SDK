# Mplify W100 SD-WAN Service Schemas and Developer Guide - Cfc#3

## Download Link

Download the entire set of schemas by clicking [here](https://github.com/MEF-GIT/MEF-LSO/tree/develop_sdWan_service/schema/serviceSchema/sdWan)

## Introduction

This repository contains the Mplify W100 SD-WAN Service Schemas and Developer Guide and corresponding YAML schemas. The work is based on MEF 70.2 SD-WAN Service Attributes and Framework. It includes YAML definitions for the following resources:

- SD-WAN UNI
- SD-WAN VC
- SD-WAN End Point
- Underlay Connectivity UNI
- Underlay Connectivity VC
- Underlay Connectivity End Point

It also provides Common, IP Common and SD-WAN Common YAML Schemas:

  - Policy
  - Security Policy
  - Application Flows
  - Common across SD-WAN and other Products and Services
  - Common IP resources
  - Common SD-WAN resources

## High-level release notes

- All resource have been submitted for a Call for Comment Review (Cfc#3) and updated to follow the resources (objects) and associated attributes as defined in MEF 70.2. The updates since Janis Release are primarily
alignment with common YAML resources that are shared with other Service (and Product) schemas. These include,
but are not limited to IP, IP common and general common resources.

  - Mplify W100 SD-WAN Service Schemas and Developer Guide v0.3.docx
- YAML Schemas:

  - sdWanCommon.yaml
  - sdWanTypes.yaml
  - sdWanUni.yaml
  - swVc.yaml
  - swVcEndPoint.yaml
  - ucs.yaml
  - ucsEndPoint.yaml
  - ucsUni.yaml
  - common.yaml
  - ipCommon.yaml
  - ipRoutingProtocolsCommon.yaml

## Maturity Level

The API files contained in this SDK are evolving and subject to change. They are based on documents that are either ratified standards or draft standards that have not yet completed the review cycles and approvals necessary to achieve the status as a Mplify standard. Mplify is making these publicly available at this time to invite wider industry review.

## Contents

This SDK contains the following items:

- `COPYRIGHT` - Copyright 2025 Mplify Alliance
- `LICENSE` - Contains a copy of the Apache 2.0 license
- `README` - This file
- `documentation` - All related standards and Developer Guides
- `Service Schema` - Service Specification schemas for:
  - `sdWan` - SD-WAN service Schemas

## Issues, Questions, and Feedback

**NOTE:** All artifacts included in this repository have line numbers. When referring to specific content in any of these artifacts, please quote the line numbers to which you are referring.

## Copyright

© Mplify Forum 2025. All Rights Reserved.

## Disclaimer

The information in this publication is freely available for reproduction and use
by any recipient and is believed to be accurate as of its publication date. Such
information is subject to change without notice and Mplify Alliance (Mplify) is not
responsible for any errors. Mplify does not assume responsibility to update or
correct any information in this publication. No representation or warranty,
expressed or implied, is made by Mplify concerning the completeness, accuracy, or
applicability of any information contained herein and no liability of any kind
shall be assumed by Mplify as a result of reliance upon such information.

The information contained herein is intended to be used without modification by
the recipient or user of this document. Mplify is not responsible or liable for any
modifications to this document made by any other party.

The receipt or any use of this document or its contents does not in any way
create, by implication or otherwise:

(a) any express or implied license or right to or under any patent, copyright,
trademark or trade secret rights held or claimed by any Mplify member which are or
may be associated with the ideas, techniques, concepts or expressions contained
herein; nor

(b) any warranty or representation that any Mplify member will announce any
product(s) and/or service(s) related thereto, or if such announcements are made,
that such announced product(s) and/or service(s) embody any or all of the ideas,
technologies, or concepts contained herein; nor

(c) any form of relationship between any Mplify member and the recipient or user of
this document.

Implementation or use of specific Mplify standards, specifications, or
recommendations will be voluntary, and no Member shall be obliged to implement
them by virtue of participation in Mplify Alliance. Mplify is a non-profit international
organization to enable the development and worldwide adoption of agile, assured,
and orchestrated network services. Mplify does not, expressly or otherwise, endorse
or promote any specific products or services.