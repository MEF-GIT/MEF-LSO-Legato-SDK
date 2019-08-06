# MEF-LSO-Legato-SDK (R3)

This repository contains the MEF LSO Legato SDK. It includes API definitions for the following functional areas:

*  Service Catalog
*  Service Ordering
*  Service Inventory
*  Service Notification

The MEF LSO Legato SDK is released under the Apache 2.0 license.

More information about the LSO Legato API reference point can be found here:

https://wiki.mef.net/display/CESG/LSO+Legato

## Maturity Level
The API files contained in this SDK are evolving and subject to change. They are based on documents that are either ratified standards, or draft standards that have not yet completed the review cycles and approvals necessary to achieve the status as a MEF standard.  MEF is making these publicly available at this time to invite wider industry review.

## Contents

This SDK contains the following items:

*  COPYRIGHT - Copyright 2019 MEF Forum
*  LICENSE - Contains a copy of the Apache 2.0 license
*  README - This file
*  api - Definitions of the API are found in this directory
	*  service-catalog - Contains the API definitions for querying and retrieving _Service-Specification_ instances from the service catalog system in the SOF.
	*  service-inventory - Contains the API definitions for querying and retrieving _Service_ instances from the service inventory system in the SOF.
	*  service-order - Contains the API definitions for posting _Service-Order_ request to the service order system in the SOF. Each _Service-Order_ contains one or more _Service-Order-Items_, each of which specifies the Service instance (and its characteristics) to be added/updated/deleted. 
	*  hub - Contains the API definitions for registering _Notification-Listeners_ to be called-back when the specified condition occurs.
* documentation
  * uml_gendoc - Contains the model diagrams and description using the _papyrus-gendoc_ tool
*  payload_description - Common descriptors are found in this directory
	*  service_schema – Contains sample OpenAPI 3.0 schema files for MSCM Carrier Ethernet (EVC_OVC) & SD-WAN services
* uml_model - Contains the Papyrus UML information model for the API interfaces and the data exchanges.
	*  MSCM – Contains UML models for MEF Services Common Model

All superseded files can be found in the Git history, if needed.


## Reference Implementations

A reference implementation of the MEF Service Instantiation API may be available from the ONAP EXTAPI project.

https://wiki.onap.org/display/DW/External+API+Framework+Project

An instance of the ONAP project may be provided in MEFnet for MEF members to undertake integration testing. Please see the MEFnet Terms of Use.

https://wiki.mef.net/display/CESG/MEFnet

https://mef.net/TOU


## Commercial Implementations


## Related Projects

The MEF Legato IPS is based on ONAP EXternal API (dublin) which can be found here:

https://docs.onap.org/en/latest/submodules/externalapi/nbi.git/docs/offeredapis/offeredapis.html

## Copyright

© MEF Forum 2019. All Rights Reserved.
