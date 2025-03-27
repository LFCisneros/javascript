# UpdatePhoneNumberRequestBody

## Example Usage

```typescript
import { UpdatePhoneNumberRequestBody } from '@clerk/backend-sdk/models/operations';

let value: UpdatePhoneNumberRequestBody = {};
```

## Fields

| Field                     | Type      | Required           | Description                                                                                                                                                                                                                  |
| ------------------------- | --------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `verified`                | _boolean_ | :heavy_minus_sign: | The phone number will be marked as verified.                                                                                                                                                                                 |
| `primary`                 | _boolean_ | :heavy_minus_sign: | Set this phone number as the primary phone number for the user.                                                                                                                                                              |
| `reservedForSecondFactor` | _boolean_ | :heavy_minus_sign: | Set this phone number as reserved for multi-factor authentication.<br/>The phone number must also be verified.<br/>If there are no other reserved second factors, the phone number will be set as the default second factor. |
