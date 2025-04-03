# OrganizationMemberships

(_organizationMemberships_)

## Overview

### Available Operations

- [create](#create) - Create a new organization membership
- [list](#list) - Get a list of all members of an organization
- [update](#update) - Update an organization membership
- [delete](#delete) - Remove a member from an organization
- [updateMetadata](#updatemetadata) - Merge and update organization membership metadata

## create

Adds a user as a member to the given organization.
Only users in the same instance as the organization can be added as members.

This organization will be the user's [active organization] (https://clerk.com/docs/organizations/overview#active-organization)
the next time they create a session, presuming they don't explicitly set a
different organization as active before then.

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.organizationMemberships.create({
    organizationId: '<id>',
    requestBody: {
      userId: '<id>',
      role: '<value>',
    },
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { organizationMembershipsCreate } from '@clerk/backend-sdk/funcs/organizationMembershipsCreate.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await organizationMembershipsCreate(clerk, {
    organizationId: '<id>',
    requestBody: {
      userId: '<id>',
      role: '<value>',
    },
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter              | Type                                                                                                             | Required           | Description                                                                                                                                                                    |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.CreateOrganizationMembershipRequest](../../models/operations/createorganizationmembershiprequest.md) | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                                                   | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                          | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                                                    | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.OrganizationMembership](../../models/components/organizationmembership.md)\>**

### Errors

| Error Type         | Status Code        | Content Type     |
| ------------------ | ------------------ | ---------------- |
| errors.ClerkErrors | 400, 403, 404, 422 | application/json |
| errors.APIError    | 4XX, 5XX           | \*/\*            |

## list

Retrieves all user memberships for the given organization

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.organizationMemberships.list({
    organizationId: '<id>',
    lastActiveAtBefore: 1700690400000,
    lastActiveAtAfter: 1700690400000,
    createdAtBefore: 1730160000000,
    createdAtAfter: 1730160000000,
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { organizationMembershipsList } from '@clerk/backend-sdk/funcs/organizationMembershipsList.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await organizationMembershipsList(clerk, {
    organizationId: '<id>',
    lastActiveAtBefore: 1700690400000,
    lastActiveAtAfter: 1700690400000,
    createdAtBefore: 1730160000000,
    createdAtAfter: 1730160000000,
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter              | Type                                                                                                           | Required           | Description                                                                                                                                                                    |
| ---------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.ListOrganizationMembershipsRequest](../../models/operations/listorganizationmembershipsrequest.md) | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                                                 | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                        | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                                                  | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.OrganizationMemberships](../../models/components/organizationmemberships.md)\>**

### Errors

| Error Type         | Status Code | Content Type     |
| ------------------ | ----------- | ---------------- |
| errors.ClerkErrors | 401, 422    | application/json |
| errors.APIError    | 4XX, 5XX    | \*/\*            |

## update

Updates the properties of an existing organization membership

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.organizationMemberships.update({
    organizationId: '<id>',
    userId: '<id>',
    requestBody: {
      role: '<value>',
    },
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { organizationMembershipsUpdate } from '@clerk/backend-sdk/funcs/organizationMembershipsUpdate.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await organizationMembershipsUpdate(clerk, {
    organizationId: '<id>',
    userId: '<id>',
    requestBody: {
      role: '<value>',
    },
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter              | Type                                                                                                             | Required           | Description                                                                                                                                                                    |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.UpdateOrganizationMembershipRequest](../../models/operations/updateorganizationmembershiprequest.md) | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                                                   | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                          | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                                                    | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.OrganizationMembership](../../models/components/organizationmembership.md)\>**

### Errors

| Error Type         | Status Code | Content Type     |
| ------------------ | ----------- | ---------------- |
| errors.ClerkErrors | 404, 422    | application/json |
| errors.APIError    | 4XX, 5XX    | \*/\*            |

## delete

Removes the given membership from the organization

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.organizationMemberships.delete({
    organizationId: '<id>',
    userId: '<id>',
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { organizationMembershipsDelete } from '@clerk/backend-sdk/funcs/organizationMembershipsDelete.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await organizationMembershipsDelete(clerk, {
    organizationId: '<id>',
    userId: '<id>',
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter              | Type                                                                                                             | Required           | Description                                                                                                                                                                    |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.DeleteOrganizationMembershipRequest](../../models/operations/deleteorganizationmembershiprequest.md) | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                                                   | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                          | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                                                    | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.OrganizationMembership](../../models/components/organizationmembership.md)\>**

### Errors

| Error Type         | Status Code | Content Type     |
| ------------------ | ----------- | ---------------- |
| errors.ClerkErrors | 401, 404    | application/json |
| errors.APIError    | 4XX, 5XX    | \*/\*            |

## updateMetadata

Update an organization membership's metadata attributes by merging existing values with the provided parameters.
Metadata values will be updated via a deep merge. Deep means that any nested JSON objects will be merged as well.
You can remove metadata keys at any level by setting their value to `null`.

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.organizationMemberships.updateMetadata({
    organizationId: '<id>',
    userId: '<id>',
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { organizationMembershipsUpdateMetadata } from '@clerk/backend-sdk/funcs/organizationMembershipsUpdateMetadata.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await organizationMembershipsUpdateMetadata(clerk, {
    organizationId: '<id>',
    userId: '<id>',
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter              | Type                                                                                                                             | Required           | Description                                                                                                                                                                    |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.UpdateOrganizationMembershipMetadataRequest](../../models/operations/updateorganizationmembershipmetadatarequest.md) | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                                                                   | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                          | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                    | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.OrganizationMembership](../../models/components/organizationmembership.md)\>**

### Errors

| Error Type         | Status Code   | Content Type     |
| ------------------ | ------------- | ---------------- |
| errors.ClerkErrors | 400, 404, 422 | application/json |
| errors.APIError    | 4XX, 5XX      | \*/\*            |
