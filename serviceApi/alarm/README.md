# Alarm Management Release notes

## Release Janis:

**Readiness status**: Call for Comments Ballot #2. Work in progress and is subject to change.

**Summary:**

- Updated Alarm model after Call for Comments Ballot #1

### List of changes in the API:

**alarmManagement.api.yaml:**
## Paths & Endpoints

### `/alarm` (GET)
- **Response Schema:**  
  - Was: returns `Alarm_Find`  
  - Now: returns `Alarm_Common`
- **Schema References:**  
  - Query parameter schemas now use `$ref` for enums (e.g., `AlarmType`, `PerceivedSeverity`, `PlannedOutageIndicator`, `AlarmState`), rather than inline enum definitions.

### `/hub` (POST) and `/hub/{id}`
- **Subscription Schema:**  
  - Was: `AlarmSubscriptionInput` and `AlarmSubscription`
  - Now: `EventSubscriptionInput` and `EventSubscription`
  - Event subscription input/output objects renamed and extended to allow event filtering.

## Schema & Components Changes

- **`Alarm_Find` type** removed, replaced by direct use of `Alarm_Common`.
- **`AlarmSubscription`/`AlarmSubscriptionInput`** renamed to `EventSubscription`/`EventSubscriptionInput`, and now supports multi-event filtering.
- **`AlarmedObjectRef`:**  
  - `@referredType` is now a required field.

### New/Refined Schemas

- **Enums as Components:**  
  - Inline enums replaced with reusable schemas: `AlarmType`, `AlarmState`, `PlannedOutageIndicator`, `ProbableCause`.
- **`ServiceRef`:**  
  - Now requires both `href` and `id` fields.

### `Alarm_Common`
- `alarmRaisedTime` is now a required field.
- `serviceAffecting` is now required.
- Enum fields use `$ref` instead of inline definitions.

### `Alarm`
- `alarmedObject` and `isRootCause` are now required.
- `probableCause` now references `ProbableCause`.

### `EventSubscriptionInput`
- `query` now allows subscribing to multiple event types, not just one.
- Enhanced documentation for event subscription syntax.

### **New Error Schema**
- `Error409` introduced for HTTP 409 (Conflict).

### **Error Schema Updates**
- `Error422` codes streamlined; some codes removed for clarity.

**alarmNotification.api.yaml:**
## Paths & Endpoints

- **Event Endpoints Expanded:**  
  - introduced four event-specific endpoints:
    - `/listener/alarmCreateEvent` (create alarm notifications)
    - `/listener/alarmDeleteEvent` (delete alarm notifications)
    - `/listener/alarmAttributeValueChangeEvent` (attribute value change notifications)
    - `/listener/alarmStateChangeEvent` (state change notifications)
  - Each endpoint uses a dedicated operationId (e.g., `alarmCreateEvent`, `alarmDeleteEvent`, etc.).

- **Request Body Schema:**  
  - A new `AlarmEvent` wrapper (with type and payload). Each event type is modeled as a specific event object, but the endpoint request uses the generic `AlarmEvent`.

## Schema & Components Changes

- **New Event Classes Introduced:**
  - `AlarmEvent`, `AlarmAttributeValueChangeEvent`, `AlarmCreateEvent`, `AlarmDeleteEvent`, `AlarmStateChangeEvent`
    - All inherit from `Event`
    - All use a payload object, `AlarmEventPayload`, which contains the actual `Alarm` object.

- **Event Type Distinction:**  
  - Each event type is distinguished by an explicit `eventType` field (enum).

- **AlarmEventPayload:**  
  - Wraps the `alarm` object.

### Alarm Object Changes

- **Required Fields:**  
  - `isRootCause` is now required for `Alarm`.
  - In `AlarmedObjectRef`, both `id` and `@referredType` are required.

- **Probable Cause Enum:**  
  - Now a standalone schema and referenced in `Alarm`.

- **PerceivedSeverity, PlannedOutageIndicator:**  
  - Now referenced as reusable schemas.

### Event Base Class

- **Event:**  
  - New base class for all event types, with fields: `eventId`, `eventTime`, `eventType`, and `event`.
  

## Release Irene:

**Readiness status**: Work in progress and is subject to change. Ready for
CfC#1.

First release of this API.