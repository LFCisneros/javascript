# UpdateOrganizationRequestBody

## Example Usage

```typescript
import { UpdateOrganizationRequestBody } from '@clerk/backend-sdk/models/operations';

let value: UpdateOrganizationRequestBody = {};
```

## Fields

| Field                   | Type                  | Required           | Description                                                                                                                     |
| ----------------------- | --------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| `publicMetadata`        | Record<string, _any_> | :heavy_minus_sign: | Metadata saved on the organization, that is visible to both your frontend and backend.                                          |
| `privateMetadata`       | Record<string, _any_> | :heavy_minus_sign: | Metadata saved on the organization that is only visible to your backend.                                                        |
| `name`                  | _string_              | :heavy_minus_sign: | The new name of the organization.<br/>May not contain URLs or HTML.<br/>Max length: 256                                         |
| `slug`                  | _string_              | :heavy_minus_sign: | The new slug of the organization, which needs to be unique in the instance                                                      |
| `maxAllowedMemberships` | _number_              | :heavy_minus_sign: | The maximum number of memberships allowed for this organization                                                                 |
| `adminDeleteEnabled`    | _boolean_             | :heavy_minus_sign: | If true, an admin can delete this organization with the Frontend API.                                                           |
| `createdAt`             | _string_              | :heavy_minus_sign: | A custom date/time denoting _when_ the organization was created, specified in RFC3339 format (e.g. `2012-10-20T07:15:20.902Z`). |
