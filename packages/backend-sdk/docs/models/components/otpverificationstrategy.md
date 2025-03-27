# OTPVerificationStrategy

## Example Usage

```typescript
import { OTPVerificationStrategy } from "@clerk/backend-sdk/models/components";

let value: OTPVerificationStrategy = "reset_password_email_code";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"phone_code" | "email_code" | "reset_password_email_code" | Unrecognized<string>
```