# ServerLog

## Example Usage

```typescript
import { ServerLog } from "waveshield/models";

let value: ServerLog = {};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `id`                                                                                          | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `type`                                                                                        | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `details`                                                                                     | [models.ServerLogDetails](../models/serverlogdetails.md)                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `timestamp`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `executor`                                                                                    | *string*                                                                                      | :heavy_minus_sign:                                                                            | Member ID or Name                                                                             |
| `target`                                                                                      | *string*                                                                                      | :heavy_minus_sign:                                                                            | Player ID or License                                                                          |