# CreateWaitlistEntryRequestBody

## Example Usage

```typescript
import { CreateWaitlistEntryRequestBody } from "@clerk/backend-sdk/models/operations";

let value: CreateWaitlistEntryRequestBody = {
  emailAddress: "Maximo.Schulist@hotmail.com",
};
```

## Fields

| Field                                                                                                                   | Type                                                                                                                    | Required                                                                                                                | Description                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `emailAddress`                                                                                                          | *string*                                                                                                                | :heavy_check_mark:                                                                                                      | The email address to add to the waitlist                                                                                |
| `notify`                                                                                                                | *boolean*                                                                                                               | :heavy_minus_sign:                                                                                                      | Optional flag which denotes whether a confirmation email should be sent to the given email address.<br/>Defaults to `true`. |