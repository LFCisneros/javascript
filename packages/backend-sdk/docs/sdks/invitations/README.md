# Invitations

(_invitations_)

## Overview

### Available Operations

- [create](#create) - Create an invitation
- [list](#list) - List all invitations
- [bulkCreate](#bulkcreate) - Create multiple invitations
- [revoke](#revoke) - Revokes an invitation

## create

Creates a new invitation for the given email address and sends the invitation email.
Keep in mind that you cannot create an invitation if there is already one for the given email address.
Also, trying to create an invitation for an email address that already exists in your application will result to an error.

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.invitations.create();

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { invitationsCreate } from '@clerk/backend-sdk/funcs/invitationsCreate.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await invitationsCreate(clerk);

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

| Parameter              | Type                                                                                             | Required           | Description                                                                                                                                                                    |
| ---------------------- | ------------------------------------------------------------------------------------------------ | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.CreateInvitationRequestBody](../../models/operations/createinvitationrequestbody.md) | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                                   | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)          | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                                    | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Invitation](../../models/components/invitation.md)\>**

### Errors

| Error Type         | Status Code | Content Type     |
| ------------------ | ----------- | ---------------- |
| errors.ClerkErrors | 400, 422    | application/json |
| errors.APIError    | 4XX, 5XX    | \*/\*            |

## list

Returns all non-revoked invitations for your application, sorted by creation date

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.invitations.list({});

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { invitationsList } from '@clerk/backend-sdk/funcs/invitationsList.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await invitationsList(clerk, {});

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

| Parameter              | Type                                                                                    | Required           | Description                                                                                                                                                                    |
| ---------------------- | --------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.ListInvitationsRequest](../../models/operations/listinvitationsrequest.md)  | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                          | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options) | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                           | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Invitation[]](../../models/.md)\>**

### Errors

| Error Type      | Status Code | Content Type |
| --------------- | ----------- | ------------ |
| errors.APIError | 4XX, 5XX    | \*/\*        |

## bulkCreate

Use this API operation to create multiple invitations for the provided email addresses. You can choose to send the
invitations as emails by setting the `notify` parameter to `true`. There cannot be an existing invitation for any
of the email addresses you provide unless you set `ignore_existing` to `true` for specific email addresses. Please
note that there must be no existing user for any of the email addresses you provide, and this rule cannot be bypassed.

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.invitations.bulkCreate();

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClerkCore } from '@clerk/backend-sdk/core.js';
import { invitationsBulkCreate } from '@clerk/backend-sdk/funcs/invitationsBulkCreate.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await invitationsBulkCreate(clerk);

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

| Parameter              | Type                                                                                    | Required           | Description                                                                                                                                                                    |
| ---------------------- | --------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.RequestBody[]](../../models/.md)                                            | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                          | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options) | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                           | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Invitation[]](../../models/.md)\>**

### Errors

| Error Type         | Status Code | Content Type     |
| ------------------ | ----------- | ---------------- |
| errors.ClerkErrors | 400, 422    | application/json |
| errors.APIError    | 4XX, 5XX    | \*/\*            |

## revoke

Revokes the given invitation.
Revoking an invitation will prevent the user from using the invitation link that was sent to them.
However, it doesn't prevent the user from signing up if they follow the sign up flow.
Only active (i.e. non-revoked) invitations can be revoked.

### Example Usage

```typescript
import { Clerk } from '@clerk/backend-sdk';

const clerk = new Clerk({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const result = await clerk.invitations.revoke({
    invitationId: '<id>',
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
import { invitationsRevoke } from '@clerk/backend-sdk/funcs/invitationsRevoke.js';

// Use `ClerkCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const clerk = new ClerkCore({
  bearerAuth: process.env['CLERK_BEARER_AUTH'] ?? '',
});

async function run() {
  const res = await invitationsRevoke(clerk, {
    invitationId: '<id>',
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

| Parameter              | Type                                                                                     | Required           | Description                                                                                                                                                                    |
| ---------------------- | ---------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`              | [operations.RevokeInvitationRequest](../../models/operations/revokeinvitationrequest.md) | :heavy_check_mark: | The request object to use for the request.                                                                                                                                     |
| `options`              | RequestOptions                                                                           | :heavy_minus_sign: | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions` | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)  | :heavy_minus_sign: | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`      | [RetryConfig](../../lib/utils/retryconfig.md)                                            | :heavy_minus_sign: | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.InvitationRevoked](../../models/components/invitationrevoked.md)\>**

### Errors

| Error Type         | Status Code | Content Type     |
| ------------------ | ----------- | ---------------- |
| errors.ClerkErrors | 400, 404    | application/json |
| errors.APIError    | 4XX, 5XX    | \*/\*            |
