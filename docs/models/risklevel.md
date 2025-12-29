# RiskLevel

## Example Usage

```typescript
import { RiskLevel } from "waveshield/models";

let value: RiskLevel = "CRITICAL";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"LOW" | "MEDIUM" | "HIGH" | "CRITICAL" | Unrecognized<string>
```