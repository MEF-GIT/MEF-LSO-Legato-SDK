# Service Inventory Management: Release notes

## Release Janis:

**Readiness status**: Requested Letter Ballot. It will be most likely published
as a standard without further changes.

**Summary:**

- Fixed `Service` missing `id` Fixed `ServiceOrderItemRef` to require
  `serviceOrderId`
- Added `@type` to Service get list filter criteria

### List of changes in the API:

**serviceInventoryManagement.api.yaml:**

- `GET /service`:

  - added `@type` to query params

- `Service`:
  - `id` - added
  - `href` - added
  - `state` - made required
- `ServiceRef`:
  - `href` - removed `format: uri`
- `ServiceOrderItemRef`:
  - `serviceOrderId` - marked as required

**serviceInventoryNotification.api.yaml:**

No changes

## Release Irene:

**Readiness status**: Call for Comments Ballot #1. Work in progress and is
subject to change.

**Summary:**

- Updating Address model according to new definition in MEF 150
- Revised, fully specialized Event model.
- State change events now carry the value of the new `state`

### List of changes in the API:

**serviceInventoryManagement.api.yaml:**

- `POST /hub`:
  - `422` - response code added
- `DELETE /hub/(id)`:

  - `422` - response code added

- `ContactInformation` - added
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
- `Service`:
  - `place` - changed ref type to `RelatedPlaceRefOrQuery`

**serviceInventoryNotification.api.yaml:**

- `408` - response code removed
- `Error408` - removed

- `ServiceEventType` - removed

- `ServiceAttributeValueChangeEvent` - added
- `ServiceCreateEvent` - added
- `ServiceDeleteEvent` - added
- `ServiceEvent` - removed
- `ServiceEventType` - removed
- `ServiceStateChangeEvent` - added
- `ServiceStateChangeEventPayload` - added
- `ServiceStateType` - added

## Release Grace:

**Readiness status**: MEF Published Standard

**Summary** - No changes.

## Release Fergie:

**Readiness status**: Requested Letter Ballot. It will be most likely published
as a standard without further changes.

**Summary** - No changes.

## Release Ella:

**Readiness status**: Starting Call for Comments Ballot #1

**Summary** - Synchronization with Sonata API patterns

- Changed files' organization to align with Sonata patterns. Mow there are only
  2 individual files:
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
  - `/listener/serviceCreateNotification` - renamed to
    `/listener/serviceCreateEvent`
  - `/listener/serviceDeleteNotification` - renamed to
    `/listener/serviceDeleteEvent`
  - `/listener/serviceStateChangeNotification` - renamed to
    `/listener/serviceStateChangeEvent`
  - `/listener/serviceAttributeValueChangeEvent` - added
- `ServiceCreateNotification` - replaced with `ServiceEvent`
- `serviceDeleteNotification` - replaced with `ServiceEvent`
- `serviceStateChangeNotification` - replaced with `ServiceEvent`
- `ServiceEventPayload` - added
- `ServiceEventType` - added
