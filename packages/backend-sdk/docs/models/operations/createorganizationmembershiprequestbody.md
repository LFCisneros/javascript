# CreateOrganizationMembershipRequestBody

## Example Usage

```typescript
import { CreateOrganizationMembershipRequestBody } from '@clerk/backend-sdk/models/operations';

let value: CreateOrganizationMembershipRequestBody = {
  userId: '<id>',
  role: '<value>',
};
```

## Fields

| Field    | Type     | Required           | Description                                                                                                                                                                                             |
| -------- | -------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `userId` | _string_ | :heavy_check_mark: | The ID of the user that will be added as a member in the organization.<br/>The user needs to exist in the same instance as the organization and must not be a member of the given organization already. |
| `role`   | _string_ | :heavy_check_mark: | The role that the new member will have in the organization.                                                                                                                                             |
