# Player

## Overview

Player Profiles & Scoring

### Available Operations

* [search](#search) - Search Players
* [get](#get) - Player Profile
* [getServers](#getservers) - Server History
* [getBans](#getbans) - Player Active Bans
* [getBansHistory](#getbanshistory) - Player Ban History
* [getThreatScore](#getthreatscore) - Threat Score
* [analyze](#analyze) - Player Analysis
* [discordLookup](#discordlookup) - Discord Lookup

## search

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/search" method="get" path="/v1/player/search" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.search({
    name: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerSearch } from "waveshield/funcs/playerSearch.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerSearch(waveShield, {
    name: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerSearch failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerSearchRequest](../../models/operations/getv1playersearchrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1PlayerSearchResponse](../../models/operations/getv1playersearchresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## get

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/{identifier}" method="get" path="/v1/player/{identifier}" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.get({
    identifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerGet } from "waveshield/funcs/playerGet.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerGet(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerIdentifierRequest](../../models/operations/getv1playeridentifierrequest.md)                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1PlayerIdentifierResponse](../../models/operations/getv1playeridentifierresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getServers

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/{identifier}/servers" method="get" path="/v1/player/{identifier}/servers" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.getServers({
    identifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerGetServers } from "waveshield/funcs/playerGetServers.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerGetServers(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerGetServers failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerIdentifierServersRequest](../../models/operations/getv1playeridentifierserversrequest.md)                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1PlayerIdentifierServersResponse](../../models/operations/getv1playeridentifierserversresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getBans

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/{identifier}/bans" method="get" path="/v1/player/{identifier}/bans" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.getBans({
    identifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerGetBans } from "waveshield/funcs/playerGetBans.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerGetBans(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerGetBans failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerIdentifierBansRequest](../../models/operations/getv1playeridentifierbansrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1PlayerIdentifierBansResponse](../../models/operations/getv1playeridentifierbansresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getBansHistory

Cost 10

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/{identifier}/bans-history" method="get" path="/v1/player/{identifier}/bans-history" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.getBansHistory({
    identifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerGetBansHistory } from "waveshield/funcs/playerGetBansHistory.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerGetBansHistory(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerGetBansHistory failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerIdentifierBansHistoryRequest](../../models/operations/getv1playeridentifierbanshistoryrequest.md)                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1PlayerIdentifierBansHistoryResponse](../../models/operations/getv1playeridentifierbanshistoryresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getThreatScore

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/{identifier}/threat-score" method="get" path="/v1/player/{identifier}/threat-score" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.getThreatScore({
    identifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerGetThreatScore } from "waveshield/funcs/playerGetThreatScore.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerGetThreatScore(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerGetThreatScore failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerIdentifierThreatScoreRequest](../../models/operations/getv1playeridentifierthreatscorerequest.md)                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1PlayerIdentifierThreatScoreResponse](../../models/operations/getv1playeridentifierthreatscoreresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## analyze

Performs a deep analysis of the player, including alt accounts, bans, and threat score.
(Cost: 15)


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/{identifier}/analysis" method="get" path="/v1/player/{identifier}/analysis" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.analyze({
    identifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerAnalyze } from "waveshield/funcs/playerAnalyze.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerAnalyze(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerAnalyze failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerIdentifierAnalysisRequest](../../models/operations/getv1playeridentifieranalysisrequest.md)                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.PlayerAnalysis](../../models/playeranalysis.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## discordLookup

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/player/{identifier}/discord-lookup" method="get" path="/v1/player/{identifier}/discord-lookup" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.player.discordLookup({
    identifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { playerDiscordLookup } from "waveshield/funcs/playerDiscordLookup.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await playerDiscordLookup(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("playerDiscordLookup failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1PlayerIdentifierDiscordLookupRequest](../../models/operations/getv1playeridentifierdiscordlookuprequest.md)                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1PlayerIdentifierDiscordLookupResponse](../../models/operations/getv1playeridentifierdiscordlookupresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |