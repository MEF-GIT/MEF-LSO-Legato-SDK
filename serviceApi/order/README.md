# Service Order Management: Release notes

## Release Kylie:

**Readiness status**: Published Standard

**Summary:**

Minor clarification changes:

- Clarified that modification of place and service relationships depends on the
  service specification
- Split `ServiceOrderStateType` to also include `ServiceOrderItemStateType`.

Document:

- [R27] - reworded to allow modification of place and/or service relationships
- [R28] - removed and replaced with new one.
- [R28] - added to clarify that the service specification defines which
  attributes can be modified.
- [O3] - added
- [R29] - added (changes existing text about Error 422 into requirement)
- [R30] - added
- provided examples of Service relationship modifications

### List of changes in the API:

**serviceOrderingManagement.api.yaml:**

- `ServiceOrderItem`:
  - `state` - changed type to `ServiceOrderItemStateType`
- `ServiceOrderItemStateType` - added

**serviceOrderingNotification.api.yaml:**

- `ServiceOrderItemStateChangeEventPayload`:
  - `state` - changed type to `ServiceOrderItemStateType`
- `ServiceOrderItemStateType` - added

## Release Janis:

**Readiness status**: Requested Letter Ballot. It will be most likely published
as a standard without further changes.

**Summary:**

Document:

- Clarified that `action=delete` only moves Service to the `terminated` state
  and not directly removes Service from the SOF's Service Inventory.
- Clarified that `partial` state only applies to `ServiceOrder`.
- Added transitions from `feasibilityChecked`, `designed`, `reserved` states to
  `terminated` for `Service`.
- Added transition from `pending` states to `failed` state for `ServiceOrder`
  and `ServiceOrderItem`.
- Removed description of `relatedContactInformation` stating that _For
  providing Notification Contact, role=notificationContact; MUST be used._
- Removed all references to `cancel` state or cancellation use case as it is
  not in the scope.

### List of changes in the API:

**serviceOrderingManagement.api.yaml:**

- `ServiceOrder`:
  - `href` - removed `format: uri`

**serviceOrderingNotification.api.yaml:**

None

## Release Irene:

**Readiness status**: Call for Comments Ballot #1. Work in progress and is
subject to change.

**Summary:**

- Updating Address model according to new definition in MEF 150
- Revised, fully specialized Event model.
- State change events now carry the value of the new `state`
- `buyerId` and `sellerId` in notification now carried vie query params
  (consistent with seller side API)

### List of changes in the API:

**serviceOrderingManagement.api.yaml:**

- `POST /hub`:
  - `422` - response code added
- `DELETE /hub/(id)`:
  - `422` - response code added
- `GET /serviceOrder:`

  - `422` - response code added

- `ContactInformation` - added
- `Duration`:
  - `amount` - added `minimum:0`
- `FieldedAddress` - replaced with `FieldedAddressRepresentation`
  - `allOf` with `GeographicAddress` - removed
  - `buildingName` - added
  - `country` - removed
  - `countryCode` - added
  - `geographicSubAddress` - removed
  - `language` - added
  - `poBox` - added
  - `privateStreetName` - added
  - `privateStreetNumber` - added
  - `streetPreDirection` - added
  - `streetPostDirection` - added
  - `streetSuffix` - removed
  - no attribute is required anymore
- `FieldedAddressValue` - replaced with `FieldedAddressRepresentation`
- `FormattedAddress` - replaced with `FormattedAddressRepresentation`
  - `addrLine1` - renamed to `formattedAddress`
  - `allOf` with `GeographicAddress` - removed
  - `addrLine2` - removed
  - `city` - removed
  - `country` - removed
  - `language` - added
  - `locality` - removed
  - `postcode` - removed
  - `postcodeExtension` - removed
  - `stateOrProvince` - removed
- `GeographicAddress_Query` - added
- `GeographicAddressLabel` - replaced with `LabelRepresentation`
  - `allOf` with `GeographicAddress` - removed
  - `externalReferenceId` - renamed to `label`
  - `externalReferenceType` - renamed to `administrativeAuthority`
  - `language` - added
- `GeographicAddressRef`
  - does not extend the `GeographicAddressRefOrValue`
  - `@type` - added with constant `GeographicAddressRef` value
- `GeographicPoint` - replaced with `GeographicPointRepresentation`
  - `allOf` with `GeographicAddress` - removed
  - `x` - renamed to `longitude`
  - `y` - renamed to `latitude`
  - `z` - renamed to `elevation`
- `GeographicSiteRef`
  - does not extend the `GeographicAddressRefOrValue`
  - `@type` - added with constant `GeographicSiteRef` value
- `GeographicSubAddress` - removed
- `GeographicSubAddressUnit` - renamed to `SubUnit`
- `RelatedContactInformation`:
  - `postalAddress` - changed ref type to `FieldedAddressRepresentation`
- `RelatedPlaceRefOrValue` - replaced with `RelatedPlaceRefOrQuery`
- `ServiceOrderItem_Common`:
  - `relatedContactInformation` - added
- `ServiceValue`:
  - `place` - changed ref type to `RelatedPlaceRefOrQuery`
- `TimeUnit`:
  - added:
    - `seconds`
    - `minutes`
    - `months`
    - `years`
  - removed:
    - `calendarMinutes`
    - `businessMinutes`
    - `calendarMonths`

**serviceOrderingNotification.api.yaml:**

- `408` - response code removed
- `Error408` - removed

- `Event` - made a generic Event

  - `event` - added
  - `eventType` - added

- `ServiceOrderCreateEvent` - added
- `ServiceOrderEvent` - removed
- `ServiceOrderInformationRequiredEvent` - added
- `ServiceOrderItemStateChangeEvent` - added
- `ServiceOrderItemStateChangeEventPayload` - added
- `ServiceOrderStateChangeEvent` - added
- `ServiceOrderStateChangeEventPayload` - added
- `ServiceOrderStateType` - added
- `ServiceOrderEventType` - removed

## Release Haley:

**Readiness status**: MEF Published Standard

**Summary** - No changes.

## Release Grace:

**Readiness status**: MEF Published Standard

**Summary** - No changes.

## Release Fergie:

**Readiness status**: Requested Letter Ballot. It will be most likely published
as a standard without further changes.

**Summary** - No changes.

## Release Ella:

**Readiness status**: Starting Call for Comments Ballot #3

**Summary** - Synchronization with Sonata API patterns

- Changed files' organization to align with Sonata patterns. Now there are only
  2 individual files:
  - `serviceInventoryManagement.api.yaml`
  - `serviceInventoryNotification.api.yaml`
- applied API patterns used in Sonata and Cantata APIs

### List of changes in the API:

**serviceOrderingManagement.api.yaml:**

- `ServiceOrder`
  - modified:
    - `id` - marked as required
    - `state` - marked as required
    - `orderDate` - marked as required
    - `serviceOrderItem` - marked as required, added minItems=1
- `ServiceOrder_Common`:
  - added:
    - `coordinatedAction`
    - `relatedContactInformation`
  - modified:
    - `requestedStartDate` - marked as required
    - `requestedCompletionDate` - marked as required
  - removed:
    - `notificationContact` - to be provided via `relatedContactInformation`
    - `relatedParty` - replaced with `relatedContactInformation`
- `ServiceOrder`:
  - `serviceOrderItem` - added minItems=1
- `Note`: renamed to `Note_BusSof`
  - added:
    - `id`
    - `source`
  - removed:
    - `system`
  - all attributes marked as required
- `ServiceOrderItem_Common`
  - `note` - added
  - `service` - changed to `ServiceValue`
  - marked as required:
    - `id`
    - `action`
    - `service`
- `ServiceOrderItem`:
  - `state` - marked as required
  - `terminationError` - added
- `ServiceOrderRelationship`:
  - `relationshipType` - changed to string instead of enum.
  - `serviceOrder` - renamed to `serviceOrderItem`
- `ServiceRelationship`:
  - `relationshipType` - removed enum, marked as required,
  - `service` - marked as required
- `ServiceValue`:
  - added:
    - `relatedContactInformation`
    - `externalId`
  - removed:
    - `category`
    - `relatedParty`
    - `serviceOrderItem`
    - `supportingService`
    - `supportingResource`
  - modified:
    - `place` - ref type changed to `RelatedPlaceRefOrValue`
- Added types:
  - `Note_BusSof`
  - `RelatedContactInformation`
  - `RelatedPlaceRefOrValue`
  - `FieldedAddress`
  - `FieldedAddressValue`
  - `FormattedAddress`
  - `GeographicAddressLabel`
  - `GeographicAddressRef`
  - `GeographicSiteRef`
  - `OrderCoordinatedAction`
  - `OrderItemCoordinatedAction`
  - `OrderItemCoordinationDependencyType`
  - `Duration`
  - `TerminationError`
  - `TimeUnit`
  - `ServiceActionType`
- Removed types:
  - `ActionType` - replace with ServiceActionType
  - `Addressable`
  - `Extensible`
  - `OrderRelationshipType`
  - `OrderItemRelationshipType`
  - `Place`
  - `Referenceable`
  - `RelatedPartyRef`
  - `ResourceRef`
  - `ServiceCreate` - replaced with `ServiceValue`
  - `ServiceRelationshipType`
  - `ServiceSpecificationRef`

**serviceOrderingNotification.api.yaml:**

- paths:
  - `/listener/serviceOrderCreateNotification` - renamed to
    `/listener/serviceOrderCreateEvent`
  - `/listener/serviceOrderStateChangeNotification` - renamed to
    `/listener/serviceOrderStateChangeEvent`
  - `/listener/serviceOrderItemStateChangeNotification` - renamed to
    `/listener/serviceOrderItemStateChangeEvent`
  - `/listener/serviceOrderInformationRequiredEvent` - added
- `ServiceOrderCreateNotification` - replaced with `ServiceOrderEvent`
- `ServiceOrderStateChangeNotification` - replaced with `ServiceOrderEvent`
- `ServiceOrderItemStateChangeNotification` - replaced with `ServiceOrderEvent`
- `ServiceOrderEventPayload` - added
- `ServiceOrderEventType` - added
