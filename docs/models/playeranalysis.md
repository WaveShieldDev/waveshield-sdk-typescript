# PlayerAnalysis

## Example Usage

```typescript
import { PlayerAnalysis } from "waveshield/models";

let value: PlayerAnalysis = {};
```

## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `player`                                                                   | [models.PlayerAnalysisPlayer](../models/playeranalysisplayer.md)           | :heavy_minus_sign:                                                         | N/A                                                                        |
| `altAccounts`                                                              | [models.AltAccount](../models/altaccount.md)[]                             | :heavy_minus_sign:                                                         | N/A                                                                        |
| `discordCheatServersLookup`                                                | [models.DiscordCheatServersLookup](../models/discordcheatserverslookup.md) | :heavy_minus_sign:                                                         | N/A                                                                        |
| `playerBans`                                                               | [models.AnalysisBan](../models/analysisban.md)[]                           | :heavy_minus_sign:                                                         | N/A                                                                        |
| `sameServerAltBans`                                                        | [models.AnalysisBan](../models/analysisban.md)[]                           | :heavy_minus_sign:                                                         | N/A                                                                        |
| `crossServerBans`                                                          | [models.AnalysisBan](../models/analysisban.md)[]                           | :heavy_minus_sign:                                                         | N/A                                                                        |
| `bansHistory`                                                              | [models.BansHistory](../models/banshistory.md)[]                           | :heavy_minus_sign:                                                         | N/A                                                                        |
| `threatScore`                                                              | [models.ThreatScore](../models/threatscore.md)                             | :heavy_minus_sign:                                                         | N/A                                                                        |