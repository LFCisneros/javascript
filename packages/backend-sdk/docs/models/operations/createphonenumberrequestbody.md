# CreatePhoneNumberRequestBody

## Example Usage

```typescript
import { CreatePhoneNumberRequestBody } from '@clerk/backend-sdk/models/operations';

let value: CreatePhoneNumberRequestBody = {
  userId: '<id>',
  phoneNumber: '1-937-659-0008 x78974',
};
```

## Fields

| Field                     | Type      | Required           | Description                                                                                                                                                                                                                 |
| ------------------------- | --------- | ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `userId`                  | _string_  | :heavy_check_mark: | The ID representing the user                                                                                                                                                                                                |
| `phoneNumber`             | _string_  | :heavy_check_mark: | The new phone number. Must adhere to the E.164 standard for phone number format.                                                                                                                                            |
| `verified`                | _boolean_ | :heavy_minus_sign: | When created, the phone number will be marked as verified.                                                                                                                                                                  |
| `primary`                 | _boolean_ | :heavy_minus_sign: | Create this phone number as the primary phone number for the user. Default: false, unless it is the first phone number.                                                                                                     |
| `reservedForSecondFactor` | _boolean_ | :heavy_minus_sign: | Create this phone number as reserved for multi-factor authentication. The phone number must also be verified.<br/>If there are no other reserved second factors, the phone number will be set as the default second factor. |
