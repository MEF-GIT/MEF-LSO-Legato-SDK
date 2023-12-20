# Performance Monitoring: Release notes

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