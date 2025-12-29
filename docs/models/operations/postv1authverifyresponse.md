# PostV1AuthVerifyResponse

Credentials Valid

## Example Usage

```typescript
import { PostV1AuthVerifyResponse } from "waveshield/models/operations";

let value: PostV1AuthVerifyResponse = {
  valid: true,
};
```

## Fields

| Field                                                                              | Type                                                                               | Required                                                                           | Description                                                                        | Example                                                                            |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `valid`                                                                            | *boolean*                                                                          | :heavy_minus_sign:                                                                 | N/A                                                                                | true                                                                               |
| `key`                                                                              | [operations.Key](../../models/operations/key.md)                                   | :heavy_minus_sign:                                                                 | N/A                                                                                |                                                                                    |
| `permissions`                                                                      | [operations.Permissions](../../models/operations/permissions.md)                   | :heavy_minus_sign:                                                                 | N/A                                                                                |                                                                                    |
| `rateLimit`                                                                        | [operations.RateLimit](../../models/operations/ratelimit.md)                       | :heavy_minus_sign:                                                                 | N/A                                                                                |                                                                                    |
| `meta`                                                                             | [operations.PostV1AuthVerifyMeta](../../models/operations/postv1authverifymeta.md) | :heavy_minus_sign:                                                                 | N/A                                                                                |                                                                                    |