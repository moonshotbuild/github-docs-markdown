---
source_path: "/en/rest/classroom/classroom"
title: "REST API endpoints for GitHub Classroom"
intro: "Use the REST API to interact with GitHub Classroom."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Classroom"
    href: "/en/rest/classroom"
  - title: "Classroom"
    href: "/en/rest/classroom/classroom"
---

# REST API endpoints for GitHub Classroom

Use the REST API to interact with GitHub Classroom.

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## Closed - Get an assignment

```
GET /assignments/{assignment_id}
```

Warning

Closed notice: This operation is no longer available as of August 28, 2026.
For more information, see the GitHub Classroom sunset notice.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`assignment_id`** (integer) (required)
  The unique identifier of the classroom assignment.

### HTTP response status codes

- **410** - Gone

## Closed - List accepted assignments for an assignment

```
GET /assignments/{assignment_id}/accepted_assignments
```

Warning

Closed notice: This operation is no longer available as of August 28, 2026.
For more information, see the GitHub Classroom sunset notice.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`assignment_id`** (integer) (required)
  The unique identifier of the classroom assignment.

### HTTP response status codes

- **410** - Gone

## Closed - Get assignment grades

```
GET /assignments/{assignment_id}/grades
```

Warning

Closed notice: This operation is no longer available as of August 28, 2026.
For more information, see the GitHub Classroom sunset notice.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`assignment_id`** (integer) (required)
  The unique identifier of the classroom assignment.

### HTTP response status codes

- **410** - Gone

## Closed - List classrooms

```
GET /classrooms
```

Warning

Closed notice: This operation is no longer available as of August 28, 2026.
For more information, see the GitHub Classroom sunset notice.

### HTTP response status codes

- **410** - Gone

## Closed - Get a classroom

```
GET /classrooms/{classroom_id}
```

Warning

Closed notice: This operation is no longer available as of August 28, 2026.
For more information, see the GitHub Classroom sunset notice.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`classroom_id`** (integer) (required)
  The unique identifier of the classroom.

### HTTP response status codes

- **410** - Gone

## Closed - List assignments for a classroom

```
GET /classrooms/{classroom_id}/assignments
```

Warning

Closed notice: This operation is no longer available as of August 28, 2026.
For more information, see the GitHub Classroom sunset notice.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`classroom_id`** (integer) (required)
  The unique identifier of the classroom.

### HTTP response status codes

- **410** - Gone
