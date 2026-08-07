---
source_path: "/en/graphql/reference/other"
title: "Other"
intro: "Reference documentation for GraphQL schema types in the Other category."
product: "GraphQL API"
document_type: "article"
breadcrumbs:
  - title: "GraphQL API"
    href: "/en/graphql"
  - title: "Reference"
    href: "/en/graphql/reference"
  - title: "Other"
    href: "/en/graphql/reference/other"
---

# Other

Reference documentation for GraphQL schema types in the Other category.

## Base64String - scalar

A (potentially binary) string encoded using base64.

## BigInt - scalar

Represents non-fractional signed whole numeric values. Since the value may
exceed the size of a 32-bit integer, it's encoded as a string.

## Boolean - scalar

Represents true or false values.

## CustomPropertyValue - scalar

A custom property value can be either a string or an array of strings. All
property types support only a single string value, except for the multi-select
type, which supports only a string array.

## Date - scalar

An ISO-8601 encoded date string.

## DateTime - scalar

An ISO-8601 encoded UTC date string.

## Float - scalar

Represents signed double-precision fractional values as specified by IEEE 754.

## GitObjectID - scalar

A Git object ID.

## GitRefname - scalar

A fully qualified reference name (e.g. refs/heads/master).

## GitSSHRemote - scalar

Git SSH string.

## GitTimestamp - scalar

An ISO-8601 encoded date string. Unlike the DateTime type, GitTimestamp is not converted in UTC.

## HTML - scalar

A string containing HTML code.

## id - query

ID of the object.

**Type:** ID!

## ID - scalar

Represents a unique identifier that is Base64 obfuscated. It is often used to refetch an object or as key for a cache. The ID type appears in a JSON response as a String; however, it is not intended to be human-readable. When expected as an input type, any string (such as "VXNlci0xMA==") or integer (such as 4) input value will be accepted as an ID.

## Int - scalar

Represents non-fractional signed whole numeric values. Int can represent values between -(2^31) and 2^31 - 1.

## PageInfo - object

Information about pagination in a connection.

### Fields for `PageInfo`

* `endCursor` (String): When paginating forwards, the cursor to continue.
* `hasNextPage` (Boolean!): When paginating forwards, are there more items?.
* `hasPreviousPage` (Boolean!): When paginating backwards, are there more items?.
* `startCursor` (String): When paginating backwards, the cursor to continue.

## PreciseDateTime - scalar

An ISO-8601 encoded UTC date string with millisecond precision.

## relay - query

Workaround for re-exposing the root query object. (Refer to
https://github.com/facebook/relay/issues/112 for more information.).

**Type:** Query!

## String - scalar

Represents textual data as UTF-8 character sequences. This type is most often used by GraphQL to represent free-form human-readable text.

## URI - scalar

An RFC 3986, RFC 3987, and RFC 6570 (level 4) compliant URI string.

## X509Certificate - scalar

A valid x509 certificate string.
