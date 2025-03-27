# SignInToken

Success

## Example Usage

```typescript
import { SignInToken } from "@clerk/backend-sdk/models/components";

let value: SignInToken = {
  object: "sign_in_token",
  id: "<id>",
  status: "accepted",
  userId: "<id>",
  createdAt: 310381,
  updatedAt: 373035,
};
```

## Fields

| Field                                                                        | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `object`                                                                     | [components.SignInTokenObject](../../models/components/signintokenobject.md) | :heavy_check_mark:                                                           | N/A                                                                          |
| `id`                                                                         | *string*                                                                     | :heavy_check_mark:                                                           | N/A                                                                          |
| `status`                                                                     | [components.SignInTokenStatus](../../models/components/signintokenstatus.md) | :heavy_check_mark:                                                           | N/A                                                                          |
| `userId`                                                                     | *string*                                                                     | :heavy_check_mark:                                                           | N/A                                                                          |
| `token`                                                                      | *string*                                                                     | :heavy_minus_sign:                                                           | N/A                                                                          |
| `url`                                                                        | *string*                                                                     | :heavy_minus_sign:                                                           | N/A                                                                          |
| `createdAt`                                                                  | *number*                                                                     | :heavy_check_mark:                                                           | Unix timestamp of creation.<br/>                                             |
| `updatedAt`                                                                  | *number*                                                                     | :heavy_check_mark:                                                           | Unix timestamp of last update.<br/>                                          |