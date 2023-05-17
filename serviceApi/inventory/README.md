# Service Inventory Management: Release notes

## Release Fergie:

**Readiness status**: Requested Letter Ballot. It will be most likely published
as a standard without further changes.

**Summary** - No changes.

## Release Ella:

**Readiness status**: Starting Call for Comments Ballot #1

**Summary** - Synchronization with Sonata API patterns

- Changed files' organization to align with Sonata patterns. Mow there are only 2 individual files:
  - `serviceInventoryManagement.api.yaml`
  - `serviceInventoryNotification.api.yaml`

### List of changes in the API:

**serviceInventoryManagement.api.yaml:**

- `serviceFind` operation:
  - query parameters added:
    - `state`
    - `externalId`
    - `serviceDate.lt`
    - `serviceDate.gt`
    - `startDate.lt`
    - `startDate.gt`
    - `endDate.lt`
    - `endDate.gt`
    - `serviceOrder.id`
    - `serviceOrderItem.id`
    - `geographicSite.id`
    - `geographicAddress.id`
    - `serviceType`
    - `startMode`
  - query parameters removed:
    - `relatedParty.id`
    - `serviceSpecification.id`
    - `serviceSpecification.name`
    - `fields`
- `Service`
  - removed:
    - `category`
    - `isServiceEnabled`
    - `isStateful`
    - `hasStarted`
    - `serviceSpecification`

    - `supportingResource`
    - `supportingService`
  - added:
    - `externalId`
    - `relatedContactInformation`
    - `serviceOrderItem`
  - modified:
    - `mefServiceConfiguration` - renamed to `serviceConfiguration`
    - `place` - changed ref type from `Place` to `RelatedPlaceRefOrValue`
    - `relatedParty` replaced with `relatedContactInformation`
    - `serviceOrder` - replaced to `serviceOrderItem`
    - `startMode` - added enum
- `ServiceCreate` - merged into `Service` and removed
- `ServiceRef`:
  - `@type` - removed
- `ServiceRelationship`:
  - `relationshipType` - removed enum, marked as required,
  - `service` - marked as required
- `MefServiceConfiguration`:
  - removed:
    - `@baseType`
    - `@schemaLocation`
- Added types:
  - `BusSofType`
  - `Note_BusSof`
  - `RelatedPlaceRefOrValue`
  - `FieldedAddress`
  - `FormattedAddress`
  - `GeographicAddressLabel`
  - `GeographicAddressRef`
  - `GeographicSiteRef`
  - `GeographicSubAddress`
  - `GeographicPoint`
  - `GeographicSubAddressUnit`
- Removed types:
  - `Addressable`
  - `Extensible`
  - `Referenceable`
  - `ResourceRef`
  - `RelatedPartyRef`
  - `ServiceOrderRef`
  - `ServiceRelationshipType`
  - `ServiceSpecificationRef`

**serviceInventoryNotification.api.yaml:**

- paths:
  - `/listener/serviceCreateNotification` - renamed to `/listener/serviceCreateEvent`
  - `/listener/serviceDeleteNotification` - renamed to `/listener/serviceDeleteEvent`
  - `/listener/serviceStateChangeNotification` - renamed to `/listener/serviceStateChangeEvent`
  - `/listener/serviceAttributeValueChangeEvent` - added
- `ServiceCreateNotification` - replaced with `ServiceEvent`
- `serviceDeleteNotification` - replaced with `ServiceEvent`
- `serviceStateChangeNotification` - replaced with `ServiceEvent`
- `ServiceEventPayload` - added
- `ServiceEventType` - added