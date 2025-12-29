# PostV1ServerBanRequest

## Example Usage

```typescript
import { PostV1ServerBanRequest } from "waveshield/models/operations";

let value: PostV1ServerBanRequest = {
  playerId: "<id>",
  reason: "<value>",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `playerId`         | *string*           | :heavy_check_mark: | N/A                |
| `reason`           | *string*           | :heavy_check_mark: | N/A                |
| `duration`         | *number*           | :heavy_minus_sign: | N/A                |
| `evidence`         | *string*           | :heavy_minus_sign: | N/A                |
| `by`               | *string*           | :heavy_minus_sign: | N/A                |