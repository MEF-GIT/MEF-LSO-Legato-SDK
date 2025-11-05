# Fault Management: Release notes

## Release Kylie:

**Readiness status**: Requested Letter Ballot. It will be most likely published
as a standard without further changes.

**Summary**: Multiple updates related to CfC#4.

### List of changes in the API:

**faultManagement.api.yaml:**

- Modify filters for `relatedObjectId` in `GET /trackingRecord` endpoint
- Remove endpoint `GET /trackingRecord/{id}`
- Change `GET /trackingRecord` endpoint to optional

---

- Class `TrackingRecord`
  - Renamed to `FmTrackingRecord`
  - Property `user` removed
  - Property `system` removed
  - Property `source` added
  - Property `relatedObjectId` reworked to use class `RelatedObjectRef`

- Class `RecurringSchedule`
  - `hourRange` property removed 

- Class `FaultManagementJob`
  - `rejectionReason` property removed
  - `terminationError` property added

- Class `FaultManagementReport`
  - `failureReason` property removed
  - `lastModifiedDate` property removed
  - `terminationError` property added

- Class `FaultManagementJobComplexQuery_Create`
  - `lastModifiedDate.gt` and `lastModifiedDate.lt` removed
---

- **Removed classes:**
  - `HourRange`

---

- **Added classes:**
  - `RelatedObjectRef`
  - `TerminationError`
  - `FaultManagementReportRef`

---

- **Other changes:**
  - Rebrand MEF to Mplify
  - Rename `creationDate` to `creationDateTime` in all classes
  - Rename `lastModifiedDate` to `lastTimeModified` in all classes
  - Rename `measurementDataPoint` to `measurementData`


**faultNotification.api.yaml**

- Class `Event`
  - `eventType` property added
  - `event` property added

- Class `FaultManagementJobReportPreparationErrorEventPayload`
  - `reportPreparationFailedReason` property removed

---

- **Other changes:**
  - Rebrand MEF to Mplify

## Release Janis:

**Readiness status**: Call for Comments #1 completed

**Summary**: Multiple updates related to CfC#1.

### List of changes in the API:

**faultManagement.api.yaml:**

- Unify list of tags and tag per endpoint assignment

- Endpoint GET `/faultManagementJob`
  - Introduced filtering by Service Id, Entity Id
  - Replaced explicit enum in the `state` filter with the reference to the dedicated class
  - Removed filters by `granularity` and `reportingPeriod`
  - Return full representation of `FaultManagementJob`

- Endpoint GET `/cancelFaultManagementJob`
  - Replaced explicit enum in the `state` filter with the reference to the dedicated class
  - Return full representation of `CancelFaultManagementJob`

- Endpoint GET `/modifyFaultManagementJob`
  - Replaced explicit enum in the `state` filter with the reference to the dedicated class
  - Return full representation of `ModifyFaultManagementJob`

- Endpoint POST `/faultManagementJobComplexQuery`
  - Return full representation of `FaultManagementJob`

- Endpoint GET `/faultManagementReport`
  - Introduced filtering by Service Id, Entity Id
  - Replaced explicit enum in the `state` filter with the reference to the dedicated class
  - Removed filters by `granularity` and `jobType`

- Endpoint POST `/faultManagementReportComplexQuery`
  - Return `FaultManagementReport_Find`

- Endpoint GET `/trackingRecord`
  - Return full representation of `TrackingRecord`

---

- Class `CancelFaultManagementJob`
  - Removed property `cancellationDeniedReason`

- Attributes of `CancelFaultManagementJob_Common` moved to `CancelFaultManagementJob_Create`

- Class `ModifyFaultManagementJob`
  - Removed property `modificationDeniedReason`

- Attributes of `ModifyFaultManagementJob_Common` moved to `ModifyFaultManagementJob_Create`

- Class `ModifyFaultManagementJob_Create`
  - Removed property `modificationReason`

- Attributes of `FaultManagementJob_Common` moved to `FaultManagementJob_Create`

---

- Class `FaultManagementReport`
  - Added `granularity`, `monitoredObject`, `outputFormat`, `resultFormat`, `serviceSpecificConfiguration`

- Class `FaultManagementReport_Find`
  - Added `granularity`, `outputFormat`, `resultFormat`, `serviceSpecificConfiguration`

- Class `FaultManagementReportComplexQuery_Create`
  - Changed `faultManagementJobId` to reference to `FaultManagementJob`
  - Removed filters by `lastModifiedDate`


---

- **Removed classes**:
  - `CancelFaultManagementJob_Common`
  - `CancelFaultManagementJob_Find`
  - `FaultManagementJob_Common`
  - `FaultManagementJobComplexQuery`
  - `FaultManagementReportComplexQuery`
  - `FaultManagementReportRef`
  - `ModifyFaultManagementJob_Common`
  - `ModifyFaultManagementJob_Find`
  - `TrackingRecord_Find`

---

- **Added classes**:
  - `EntityRef`
  - `MonitoredObjectRef`
  - `ServiceFromToRef`
  - `ServiceRef`

---

- **Other changes:**
  - Class `Interval` replaced by `TimeDuration`
  - Replaced `ServiceId` class with `MonitoredObjectRef` class which is a composite of `ServiceRef`, `ServiceFromToRef`, `EntityRef`
  - All `serviceId` properties replaced by `monitoredObject` property of class `MonitoredObjectRef`
  - Class `ServicePayloadSpecificAttributes` renamed to `ServiceSpecificConfiguration`
  - Class `ResultPayload` renamed to `ServiceSpecificResult`
  - Property `servicePayloadSpecificAttributes` renamed to `serviceSpecificConfiguration`
  - Properties of class `HourRange` changed format and applied pattern to force time format
  - Property `measurementDataPoints` of class `ReportContentItem` renamed to `measurementDataPoint`
  - Updated descriptions


**faultNotification.api.yaml:**

- Separate Event Type per notification type by adding the following classes:
  - `FaultManagementJobCreateEvent`
  - `FaultManagementJobStateChangeEvent`
  - `FaultManagementJobAttributeValueChangeEvent`
  - `CancelFaultManagementJobStateChangeEvent`
  - `ModifyFaultManagementJobStateChangeEvent`
  - `FaultManagementReportCreateEvent`
  - `FaultManagementReportStateChangeEvent`

- Removed generic classes:
  - `FaultManagementJobEvent`
  - `FaultManagementJobProcessEvent`
  - `FaultManagementJobProcessEventPayload`
  - `FaultManagementReportEvent`

- Introduced classes representing Event Payload per Event Type:
  - `CancelFaultManagementJobStateChangeEventPayload`
  - `FaultManagementJobStateChangeEventPayload`
  - `FaultManagementReportStateChangeEventPayload`
  - `ModifyFaultManagementJobStateChangeEventPayload`

- Removed classes representing Event Type and added Event Type directly to Event classes:
  - `FaultManagementJobEventType`
  - `FaultManagementJobReportPreparationErrorEventType`
  - `FaultManagementJobReportReadyEventType`
  - `FaultManagementJobProcessEventType`
  - `FaultManagementReportEventType`

- Removed 408 error from all endpoints

- Added missing and updated existing descriptions

- Replaced state enums with dedicated classes:
  - `FaultManagementJobProcessStateType`
  - `FaultManagementJobStateType`
  - `FaultManagementReportStateType`

## Release Irene:

**Readiness status**: Work in progress and is subject to change. Ready for
CfC#1.

First release of this API.