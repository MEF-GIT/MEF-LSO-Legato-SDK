# Mplify-LSO-Legato-SDK Kylie Release

## Download Link

Download the entire repository by clicking
[here](https://github.com/MEF-GIT/MEF-LSO-Legato-SDK/releases/download/kylie/Mplify-LSO-Legato-SDK-kylie.zip)

## Introduction

All references to 'MEF Forum' or 'MEF' in the release documentation, links, and
YAML files should be interpreted as references to 'Mplify Alliance' and
'Mplify' respectively. Since this release coincides with the transition of the
name of MEF Forum to Mplify Alliance, changes were not made to all the files in
this release. Standards that were already published will retain the "MEF" name.

## Overview

This repository contains the release of the Legato SDK. The SDK includes APIs
for Service Order, Service Inventory, Performance Monitoring, and Streaming
Management functions of the Service Orchestration Functionality (SOF) at the
LSO Legato Interface Reference Point (IRP) as defined in the Mplify LSO
Reference Architecture.

Also included are Service schemas and Performance Monitoring definitions.

## High-level release notes

MCP Server code added for every SOF side API.

- Updated documents:
  - Mplify 99.1 - LSO Service Ordering Management API - Developer Guide
  - Mplify 133.1 - Allegro, Interlude and Legato Fault Management and
    Performance Monitoring BR&UC
  - Mplify 135.1 - LSO Service Inventory Management API - Developer Guide
  - Mplify 136.1 - Allegro, Interlude, Legato Service Function Testing Business
    Requirements and Use Cases
  - Mplify 143 - Performance Monitoring API - Developer Guide
  - Mplify 146 - Alarms and Threshold Crossing Alerts (Alarms) API - Developer
    Guide
  - Mplify 148 - Fault Management API - Developer Guide
  - Mplify 149 - Service Function Testing API - Developer Guide

- No new Documents:

## Scope

It includes API definitions for the following functional areas:

- Service Catalog - This includes support for
  - Service Specification - Retrieve operations only
  - Not in scope
    - Service Specifications - Create, Amend/Modify, Delete operations
    - Service Catalog, Service Category, Service Candidate, Job/Task
- Service Ordering - This includes support for
  - Service Order/OrderItem - Create and Retrieve operations only
  - Not in scope
    - Service Order/OrderItem - Amend/Modify/Cancel, Delete operations
- Service Inventory - This includes support for
  - Service - Retrieve operations only
  - Not in scope
    - Service - Create, Amend/Modify, Delete operations
- Alarm Management
- Fault Management
- Performance Monitoring
- Service Function Testing
- Streaming Management

In addition to the Service Provisioning APIs, the SDK includes the following
Mplify Service Specification schemas:

- SD-WAN Services
- Carrier Ethernet Services
- L1 Connectivity Services
- IP/IP-VPN Services

The Mplify LSO Legato SDK is released under the Apache 2.0 license.

More information about the LSO Legato API reference point and its roadmap can
be found here:

https://wiki.mplify.net/display/CESG/LSO+Legato

## Maturity Level

The API files contained in this SDK are evolving and subject to change. They
are based on documents that are either work in progress or draft standards that
have not yet completed the review cycles and approvals necessary to achieve the
status as a Mplify standard. Mplify is making these publicly available at this
time to invite wider industry review.

The maturity per functionality is presented as follows:

(\*) is used to mark an item that changes its maturity compared to the previous
release.

APIs and Developer Guides:

- Service Catalog API - **early draft version, on hold, not to be used**
- \*Mplify 99.1 - LSO Service Ordering Management API - Developer Guide -
  **Published Standard**
- \*Mplify 135.1 - LSO Legato Service Inventory Management API - Developer
  Guide - **Published Standard**

Service Schemas:

- \*SD-WAN (Mplify W100) - **work in progress - CfC#3**
- Carrier Ethernet (Mplify 101) - **Published Standard**
- \*Internet Protocol (Mplify W102) - **Done. Ready for Letter Ballot**
- LSO Legato Service Provisioning Specification - L1 (Mplify W103) -
  **on-hold - ready for CfC#1**

SOAM:

- Mplify \*133.1 - Allegro, Interlude and Legato Fault Management and
  Performance Monitoring BR&UC - **Published Standard**
- Mplify \*136.1 - Mplify 136.1 - Allegro, Interlude, Legato Service Function
  Testing Business Requirements and Use Cases - **Published Standard**
- Mplify \*143 - Performance Monitoring API - Developer Guide - **Published
  Standard**
- Mplify \*146 - Alarms and Threshold Crossing Alerts (Alarms) API - Developer
  Guide - **Published Standard**
- Mplify 147 - Streaming Management API - Developer Guide - **Published
  Standard**
- Mplify \*148 - Fault Management API - Developer Guide - **Published
  Standard**
- Mplify \*149 - Service Function Testing API - Developer Guide - **Published
  Standard**

Security:

- MEF 128.1 - **Published Standard**

## Contents

This SDK contains the following items:

- `COPYRIGHT` - Copyright 2026 Mplify Forum
- `LICENSE` - Contains a copy of the Apache 2.0 license
- `README` - This file
- `serviceApi` - Definitions of the APIs are found in this directory, provided
  as yaml files.
- `schema` - Contains JSON schema files for service specifications.
- `documentation` - documentation including API/Schema developer guides and
  openapi-tools generated API descriptions in markdown format
  - `supportingStandards` - The rest of the documents and standards.
- `generated`
  - `mcp` - autogenerated MCP Servers for all Seller side APIs.
  - `security` - A not normative version of the standard APIs including the
    security profiles as required by MEF 128.1. Provided for evaluation.

## Issues, questions, and Feedback

Issues should be reported with the use of GitHub issues. Questions and feedback
should be asked either at
[Legato SDK Discussions](https://github.com/MEF-GIT/MEF-LSO-Legato-SDK/discussions)
or directly to community_manager@mplify.net.

## Reference Implementations

A reference implementation of the Mplify Service Instantiation API may be
available from the ONAP EXTAPI project.

https://wiki.onap.org/display/DW/External+API+Framework+Project

## Copyright

© Mplify Alliance 2026. All Rights Reserved.

**Disclaimer**

The information in this publication is freely available for reproduction and
use by any recipient and is believed to be accurate as of its publication date.
Such information is subject to change without notice and Mplify Alliance
(Mplify) is not responsible for any errors. Mplify does not assume
responsibility to update or correct any information in this publication. No
representation or warranty, expressed or implied, is made by Mplify concerning
the completeness, accuracy, or applicability of any information contained
herein and no liability of any kind shall be assumed by Mplify as a result of
reliance upon such information.

The information contained herein is intended to be used without modification by
the recipient or user of this document. Mplify is not responsible or liable for
any modifications to this document made by any other party.

The receipt or any use of this document or its contents does not in any way
create, by implication or otherwise:

- (a) any express or implied license or right to or under any patent,
  copyright, trademark or trade secret rights held or claimed by any Mplify
  member which are or may be associated with the ideas, techniques, concepts or
  expressions contained herein; nor

- (b) any warranty or representation that any Mplify member will announce any
  product(s) and/or service(s) related thereto, or if such announcements are
  made, that such announced product(s) and/or service(s) embody any or all of
  the ideas, technologies, or concepts contained herein; nor

- (c) any form of relationship between any Mplify member and the recipient or
  user of this document.

Implementation or use of specific Mplify standards, specifications or
recommendations will be voluntary, and no Member shall be obliged to implement
them by virtue of participation in Mplify Alliance. Mplify is a non-profit
international organization to enable the development and worldwide adoption of
agile, assured and orchestrated network services. Mplify does not, expressly or
otherwise, endorse or promote any specific products or services.
