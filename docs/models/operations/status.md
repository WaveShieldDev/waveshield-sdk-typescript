# Status

## Example Usage

```typescript
import { Status } from "waveshield/models/operations";

let value: Status = "OFFLINE";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"ONLINE" | "OFFLINE" | "BANNED" | Unrecognized<string>
```