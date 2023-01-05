# Service Order Management: Release notes

## Release Ella:

**Readiness status**: Starting Call for Comments Ballot #3

**Summary** - Synchronization with Sonata API patterns

- Changed files' organization to align with Sonata patterns. Now there are only 2 individual files:
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
  - `/listener/serviceOrderCreateNotification` - renamed to `/listener/serviceOrderCreateEvent`
  - `/listener/serviceOrderStateChangeNotification` - renamed to `/listener/serviceOrderStateChangeEvent`
  - `/listener/serviceOrderItemStateChangeNotification` - renamed to `/listener/serviceOrderItemStateChangeEvent`
  - `/listener/serviceOrderInformationRequiredEvent` - added
- `ServiceOrderCreateNotification` - replaced with `ServiceOrderEvent`
- `ServiceOrderStateChangeNotification` - replaced with `ServiceOrderEvent`
- `ServiceOrderItemStateChangeNotification` - replaced with `ServiceOrderEvent`
- `ServiceOrderEventPayload` - added
- `ServiceOrderEventType` - added
