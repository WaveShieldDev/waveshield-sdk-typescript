# PostV1ServerAdminAddRequest

## Example Usage

```typescript
import { PostV1ServerAdminAddRequest } from "waveshield/models/operations";

let value: PostV1ServerAdminAddRequest = {
  discordId: "<id>",
  permissions: [],
};
```

## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `discordId`                                                      | *string*                                                         | :heavy_check_mark:                                               | N/A                                                              |
| `permissions`                                                    | [operations.Permission](../../models/operations/permission.md)[] | :heavy_check_mark:                                               | N/A                                                              |