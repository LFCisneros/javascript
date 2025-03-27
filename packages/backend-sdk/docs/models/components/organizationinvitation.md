# OrganizationInvitation

An organization invitation

## Example Usage

```typescript
import { OrganizationInvitation } from "@clerk/backend-sdk/models/components";

let value: OrganizationInvitation = {
  object: "organization_invitation",
  id: "<id>",
  emailAddress: "Grayce.Kassulke84@yahoo.com",
  role: "<value>",
  roleName: "<value>",
  publicMetadata: {
    "key": "<value>",
  },
  url: "https://happy-go-lucky-formamide.com",
  expiresAt: 185232,
  createdAt: 401259,
  updatedAt: 929292,
};
```

## Fields

| Field                                                                                              | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `object`                                                                                           | [components.OrganizationInvitationObject](../../models/components/organizationinvitationobject.md) | :heavy_check_mark:                                                                                 | String representing the object's type. Objects of the same type share the same value.<br/>         |
| `id`                                                                                               | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `emailAddress`                                                                                     | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `role`                                                                                             | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `roleName`                                                                                         | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `organizationId`                                                                                   | *string*                                                                                           | :heavy_minus_sign:                                                                                 | N/A                                                                                                |
| `status`                                                                                           | *string*                                                                                           | :heavy_minus_sign:                                                                                 | N/A                                                                                                |
| `publicMetadata`                                                                                   | Record<string, *any*>                                                                              | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `privateMetadata`                                                                                  | Record<string, *any*>                                                                              | :heavy_minus_sign:                                                                                 | N/A                                                                                                |
| `url`                                                                                              | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `expiresAt`                                                                                        | *number*                                                                                           | :heavy_check_mark:                                                                                 | Unix timestamp of expiration.                                                                      |
| `createdAt`                                                                                        | *number*                                                                                           | :heavy_check_mark:                                                                                 | Unix timestamp of creation.                                                                        |
| `updatedAt`                                                                                        | *number*                                                                                           | :heavy_check_mark:                                                                                 | Unix timestamp of last update.                                                                     |