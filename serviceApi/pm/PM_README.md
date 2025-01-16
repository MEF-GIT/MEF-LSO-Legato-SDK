# Performance Monitoring: Release notes

## Release Irene:

**Readiness status**: Undergoing Call for Comments #1

**Summary**: 

- Subject of PM job was added to the API (identifiers of service or entity)
- Suspend and resume PM job changed to synchronous actions
- Cancel PM Job action changed to two-state with intermediary Pending Cancel step
- Field buyerProfileId removed from Performance Profile
- Field scheduleDefinition in PM Job changed to mandatory
- Fields granularity and reporting period of PM Profile changed to mandatory
- Schedule definition reworked to replicate behavior of Cron utility in Unix-based systems
- Changed behavior of attachment files generation to allow Seller/Server define the file location

### List of changes in the API:

**performanceMonitoring.api.yaml:**

- Removed Administrator role 
- `/performanceJob`:
  - additional filters based on Service and Entity identifiers
  - introduced new state `pendingCancel` 
- `/performanceJob/{id}/resume`:
  - Added new endpoint to execute resume action
- `/performanceJob/{id}/suspend`:
  - Added new endpoint to execute suspend action
- `/cancelPerformanceJob`:
  - Change state names of `CancelPerformanceJob`
  - Removed error code `501 Method not implemented`
- `/cancelPerformanceJob/{id}`:
  - Removed error code `501 Method not implemented`
- `/modifyPerformanceJob`:
  - Change state names of `ModifyPerformanceJob`
  - Removed error code `501 Method not implemented`
- `/modifyPerformanceJob/{id}`:
  - Removed error code `501 Method not implemented`
- `/resumePerformanceJob`
  - Endpoint removed - resume action changed to synchronous
- `/resumePerformanceJob/{id}`
  - Endpoint removed
- `/suspendPerformanceJob`
  - Endpoint removed - suspend action changed to synchronous
- `/suspendPerformanceJob/{id}`
  - Endpoint removed
- `/performanceProfile`:
  - Removed query based on `buyerProfileId`
  - Changed list of `PerformanceProfile` states
- `/performanceProfile/{id}`: 
  - Added error code `501 Method not implemented` for `delete` operation
- `/performanceReport`: 
  - additional filters based on Service and Entity identifiers
  - additional filters based on Job type
  - removed filters based on Consuming application Id an Producing application Id
- `AttachmentURL`: 
  - Added `retentionPeriod` field
- `CancelPerformanceJob`: 
  - Added mandatory reference to `PerformanceJob` 
- `CancelPerformanceJob_Common`: 
  - Removed reference to `PerformanceJob` 
- `CancelPerformanceJob_Create`:
  - Added mandatory attribute `performanceJobId`
- `Interval`: 
  - Removed option `not applicable`
- `MeasurementTime`: 
  - Removed `oneOf` clause
- `ModifyPerformanceJob`: 
  - Added mandatory reference to `PerformanceJob` 
- `ModifyPerformanceJob_Common`: 
  - Removed reference to `PerformanceJob` 
  - Removed `fileTransferData` field
- `ModifyPerformanceJob_Create`:
  - Added mandatory attribute `performanceJobId`
- `ModifyPerformanceJob_ProfileValue`
  - Renamed to `ModifyPerformanceJob_PerformanceProfileValue`
- `PerformanceJobComplexQuery`: 
  - Attributes defined by `PerformanceProfile` class moved to `performanceProfile` section
  - Added fields `lastModifiedDate`, `monitoredObjectId` (mandatory) 
- `PerformanceJobComplexQuery_Create`:
  - Added fields `lastModifiedDate.gt`, `lastModifiedDate.lt`, `monitoredObjectId`, `outputFormat`, `resultFormat`
- `PerformanceJobProcessStateType`
  - changed state names
- `PerformanceJobRef`:
  - Renamed attributes
- `PerformanceJobStateType`: 
  - New state `pendingCancel`
- `PerformanceJobValue`: 
  - Removed field `fileTransferData`
  - Added mandatory field `monitoredObjectId`
  - `granularity` changed to mandatory
- `PerformanceJob_Common`: 
  - Removed field `fileTransferData`
  - Added mandatory field `monitoredObjectId`
  - `scheduleDefinition` changed to mandatory
- `PerformanceJob_Find`: 
  - Added mandatory field `monitoredObjectId`
  - `scheduleDefinition` changed to mandatory
- `PerformanceProfile`: 
  - Removed field `rejectionReason`
- `PerformanceProfileRef`: 
  - Renamed fields
- `PerformanceProfileStateType`: 
  - Changed list of states
- `PerformanceProfileValue`: 
  - `granularity` and `reportingPeriod` changed to mandatory
- `PerformanceProfile_Common`: 
  - Removed `buyerProfileId`
  - `granularity` and `reportingPeriod` changed to mandatory
- `PerformanceProfile_Find`: 
  - Removed `buyerProfileId`
  - `granularity` and `reportingPeriod` changed to mandatory
- `PerformanceProfile_Update`: 
  - Removed `buyerProfileId`
- `PerformanceReport`: 
  - Removed attribute `performanceJob`
- `PerformanceReportComplexQuery`: 
  - Removed attributes `consumingApplicationId`, `granularity`, `outputFormat`, `producingApplicationId`, `resultFormat`, `servicePayloadSpecificAttributes`
  - Added attribute `lastModifiedDate`
  - `performanceJob` type changed to `PerformanceJobRefOrValue`
  - Attributes `creationDate`, `performanceJob`, `performanceReport`, `reportingTimeframe`, `state` changed to mandatory
- `PerformanceReportComplexQuery_Create`: 
  - Removed attribute `consumingApplicationId`, `producingApplicationId`
  - Added attributes `lastModifiedDate.gt`, `lastModifiedDate.lt`, `monitoredObjectId`
  - Attribute `performanceJob` changed to string `performanceJobId`
- `PerformanceReportRef`: 
  - Attributes names changed
- `PerformanceReport_Common`: 
  - Added mandatory field `performanceJob`
  - `reportingTimeframe` changed to mandatory
- `PerformanceReport_Create`: 
  - Removed field `performanceJob`
- `PerformanceReport_Find`: 
  - Attributes `performanceJob` and `reportingTimeframe` changed to mandatory
- `ReportContentItem`: 
  - field `measurementDataPoint` renamed
- `ScheduleDefinition`: 
  - Reworked due to recurring schedule based on Cron utility
- New classes added:
  - `EntityId` - used to specify subject of monitoring 
  - `MonitoredObjectId` - parent class used to specify subject of monitoring
  - `RecurringSchedule` - definition of recurring schedule based on Cron utility
  - `ServiceId` - used to specify subject of monitoring 
- Removed classes:
  - `DayOfMonth` - due schedule definition reworks
  - `DayOfWeek` - due schedule definition reworks
  - `FileTransferData` - behavior of attachment file changed
  - `MonthlyScheduleDayOfWeekDefinition` - due schedule definition reworks
  - `RecurringFrequency` - RecurringFrequency
  - `ResumePerformanceJob` - resume action changed to synchronous
  - `ResumePerformanceJob_Common`
  - `ResumePerformanceJob_Create`
  - `ResumePerformanceJob_Find`
  - `SuspendPerformanceJob` - suspend action changed to synchronous
  - `SuspendPerformanceJob_Common`
  - `SuspendPerformanceJob_Create`
  - `SuspendPerformanceJob_Find`

**performanceNotification.api.yaml**

- Removed endpoints: 
  - `/listener/resumePerformanceJobStateChangeEvent` - resume action changed to synchronous
  - `/listener/suspendPerformanceJobStateChangeEvent` - suspend action changed to synchronous
  - `/listener/performanceProfileStateChangeEvent` - due to removal of `PerformanceProfile` states
- `PerformanceJobEventPayload`:
  - Changed list of states in `state` field
- `PerformanceJobProcessEventType`: 
  - Removed unnecessary event types
- `PerformanceProfileEventType`:
  - Removed unnecessary event types

## Release Haley:

**Readiness status**: Call for Comments #2 completed

**Summary** - No changes.

## Release Grace:

**Readiness status**: Undergoing Call for Comments #1

**Summary**: Small updates found during the CfC process.

### List of changes in the API:

**performanceMonitoring.api.yaml:**

- `/performanceJob`:
  - `state` - enum values `inProgress` and `resourceUnavailable` changed to camelCase
- `PerformanceJobStateType`:
  - `inProgress` and `resourceUnavailable` - changed to camelCase
- `/performanceReport/{id}`:
  - query based on a single Performance Report identifier instead of an array of IDs
- `CancelPerformanceJob`:
  - `creationDate` - set to required
- `CancelPerformanceJob_Find`:
  - `creationDate` - set to required
- `FileTransferData`:
  - `compressionType` - enum values fixed
- `HourRange`:
  - added missing descriptions
- `Interval`:
  - added missing description
- `ModifyPerformanceJob`:
  - `creationDate` - set to required
- `ModifyPerformanceJob_Find`:
  - `creationDate` - set to required
- `MonthlyScheduleDayOfWeekDefinition`:
  - `recurringDaySequence` - fixed type (array)
  - `dayOfMonthRecurrence` - fixed type (array)
- `ResumePerformanceJob`:
  - `creationDate` - set to required
- `ResumePerformanceJob_Find`:
  - `creationDate` - set to required
- `ScheduleDefinition`:
  - `scheduleDefinitionHourRange` - set as a reference to `HourRange`
- `SuspendPerformanceJob`:
  - `creationDate` - set to required
- `SuspendPerformanceJob_Find`:
  - `creationDate` - set to required
- `TrackingRecord_Find`:
  - `id` - added required field
  
**performanceNotification.api.yaml**
- `PerformanceJobReportPreparationErrorEventPayload`:
  - `reportPreparationFailedReason` - marked as required

## Release Fergie:

First release of this API.