# GetV1ServerStatsResponse

Historical metrics

## Example Usage

```typescript
import { GetV1ServerStatsResponse } from "waveshield/models/operations";

let value: GetV1ServerStatsResponse = {};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `window`                                                   | *string*                                                   | :heavy_minus_sign:                                         | N/A                                                        |
| `since`                                                    | *string*                                                   | :heavy_minus_sign:                                         | N/A                                                        |
| `current`                                                  | [operations.Current](../../models/operations/current.md)   | :heavy_minus_sign:                                         | N/A                                                        |
| `averages`                                                 | [operations.Averages](../../models/operations/averages.md) | :heavy_minus_sign:                                         | N/A                                                        |
| `activity`                                                 | [operations.Activity](../../models/operations/activity.md) | :heavy_minus_sign:                                         | N/A                                                        |
| `history`                                                  | [operations.History](../../models/operations/history.md)[] | :heavy_minus_sign:                                         | N/A                                                        |