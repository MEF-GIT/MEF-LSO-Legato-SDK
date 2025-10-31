# Service Function Testing Release notes
## Release Kylie

**Readiness status**: Letter Ballot.

**Summary:**

- Updated Service Function Testing API after Call for Comments Ballot #2

### List of changes in the API:
**serviceFunctionTest.api.yaml:**

## Paths & Endpoints
- **Parameter Changes:**  
  - `/testJob` GET:
    - param `startDateTime` renamed to `requestedStartDateTime`.
    - param `endDateTime` renamed to `requestedStartDateTime`.
  - `/testResult` GET:
    - param `startDateTime` renamed to `requestedStartDateTime`.
    - param `endDateTime` renamed to `requestedStartDateTime`.

## Schema & Components Changes

- **Property Changes:**  

  - `ServiceSpecificTestResultConfguration` - corrected spelling to `ServiceSpecificTestResultConfiguration`
  - `TestJob_Common` and `TestJob_Find` property `startDateTime` renamed to  `requestedStartDateTime`.
  - `TestJob_Common` and `TestJob_Find` property `endDateTime` renamed to  `requestedEndDateTime`.
  - `TestJob_Common`:
    - property `validFor` deleted.
    - property `requestedEndDateTime` made required
  - `TestJobStateType`  enum value `assessingCancelation` corrected spelling to `assessingCancellation`
  - `TestResult`:
    - `serviceSpecificTestResultConfguration` corrected spelling to `serviceSpecificTestResultConfiguration`
## Release Janis:

**Readiness status**: Call for Comments Ballot #2. Work in progress and is subject to change.

**Summary:**

- Updated Service Function Testing API after Call for Comments Ballot #1

### List of changes in the API:
**serviceFunctionTest.api.yaml:**

## Paths & Endpoints
- **Parameter Changes:**  
  - `/testJob` GET:
  - param `relatedServiceId` split into `relatedServiceIdFrom` and `relatedServiceIdTo` for more flexible service association.
  - State enums for process job-related endpoints (`cancelTestJob`, `suspendTestJob`, `resumeTestJob`) reordered and more consistently named, but values are functionally the same.

- **Request/Response Schema Naming:**  
  - v1: POST to `/testJob` uses `TestJob_Create`
  - v2: POST to `/testJob` uses `TestJob_Common` (indicating a schema refactoring and consolidation)

- **New or Removed Endpoints:**
  - `/testResult` (GET): List Test Results (now explicitly mentioned in v2 use cases)
  - `/testResult/{id}` (GET): Retrieve Test Result by ID (now explicitly mentioned in v2 use cases)

---

## Schema & Components Changes

- **Schema Consolidation:**  
  - v2 uses more consolidated/common schemas for create/update operations (e.g., `TestJob_Common` instead of `TestJob_Create`).

- **Parameter Naming:**  
  - More precise and consistent parameter names and descriptions (notably for service association on `/testJob`).

- **Test Result Emphasis:**  
  - Test Result endpoints (`/testResult`, `/testResult/{id}`) are now more prominent in v2's documented use cases, though the paths themselves existed in v1.

**serviceFunctionTestNotification.api.yaml:**

## Paths & Endpoints

- **Base Paths:**  
  - All main event endpoints are retained, with v2 adding a new endpoint for Test Result events.

- **New/Changed Endpoints in v2:**  
  - `/listener/testResultCreateEvent`: Added for Test Result creation event notifications.
  - `/listener/testProfileLifecycleStateChangeEvent`: New, replaces or expands on `/listener/testProfileStateChangeEvent`.
  - Request body schemas for all endpoints now reference more specific event types, e.g., `TestJobCreateEvent`, `TestProfileCreateEvent` instead of generic event wrappers.

- **Request/Response Schema Naming:**  
  - v1 uses general event types (e.g., `TestJobEvent`, `TestProfileEvent`),  
    v2 uses specific event classes for each endpoint (e.g., `TestJobCreateEvent`, `TestProfileDeleteEvent`, etc.).

- **Removed/Changed Endpoints:**  
  - `/listener/testProfileStateChangeEvent` (v1) → `/listener/testProfileLifecycleStateChangeEvent` (v2)

---

## Schema & Components Changes

- **Schema Specialization:**  
  - Each notification endpoint now uses a dedicated schema class, rather than sharing a generic event wrapper.
  - Expanded event models for Test Job, Test Profile, and new Test Result notifications.

- **Test Result Events:**  
  - Newly supported in v2 for both endpoint and event schema.

- **Event Model:**  
  - v2 event schemas are more explicit, with a dedicated class for each event, including state change and attribute change events.


## Release Irene:

**Readiness status**: Work in progress and is subject to change. Ready for
CfC#1.

First release of this API.