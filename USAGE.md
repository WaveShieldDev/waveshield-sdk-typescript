<!-- Start SDK Example Usage [usage] -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.auth.verify();

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->