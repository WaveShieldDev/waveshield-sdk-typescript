# Server

## Overview

Server Management (Requires License Link)

### Available Operations

* [getInfo](#getinfo) - Server Info
* [getStats](#getstats) - Server Statistics
* [getBans](#getbans) - Server Active Bans
* [getBanHistory](#getbanhistory) - Server Ban History
* [getConfig](#getconfig) - Server Config
* [getPlayers](#getplayers) - Online Players List
* [getAdmins](#getadmins) - Server Admins
* [getLogs](#getlogs) - Server Logs
* [lookupPlayer](#lookupplayer) - Lookup Player
* [requestScreenshot](#requestscreenshot) - Request Screenshot
* [kick](#kick) - Kick Player
* [getBan](#getban) - Get Ban Info
* [ban](#ban) - Ban Player
* [banOffline](#banoffline) - Ban Player Offline
* [unban](#unban) - Unban Player
* [unbanLast](#unbanlast) - Unban Last Players
* [unbanAll](#unbanall) - Unban All Players
* [executeCommand](#executecommand) - Execute Console Command
* [addAdmin](#addadmin) - Add Admin
* [removeAdmin](#removeadmin) - Remove Admin

## getInfo

Cost 2

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server" method="get" path="/v1/server" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getInfo();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetInfo } from "waveshield/funcs/serverGetInfo.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetInfo(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetInfo failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerResponse](../../models/operations/getv1serverresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getStats

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/stats" method="get" path="/v1/server/stats" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getStats({});

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetStats } from "waveshield/funcs/serverGetStats.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetStats(waveShield, {});
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetStats failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1ServerStatsRequest](../../models/operations/getv1serverstatsrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerStatsResponse](../../models/operations/getv1serverstatsresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getBans

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/bans" method="get" path="/v1/server/bans" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getBans();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetBans } from "waveshield/funcs/serverGetBans.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetBans(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetBans failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1ServerBansRequest](../../models/operations/getv1serverbansrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerBansResponse](../../models/operations/getv1serverbansresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getBanHistory

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/bans-history" method="get" path="/v1/server/bans-history" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getBanHistory();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetBanHistory } from "waveshield/funcs/serverGetBanHistory.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetBanHistory(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetBanHistory failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1ServerBansHistoryRequest](../../models/operations/getv1serverbanshistoryrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerBansHistoryResponse](../../models/operations/getv1serverbanshistoryresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getConfig

Cost 2

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/config" method="get" path="/v1/server/config" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getConfig();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetConfig } from "waveshield/funcs/serverGetConfig.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetConfig(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetConfig failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerConfigResponse](../../models/operations/getv1serverconfigresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getPlayers

Cost 2

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/players" method="get" path="/v1/server/players" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getPlayers();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetPlayers } from "waveshield/funcs/serverGetPlayers.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetPlayers(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetPlayers failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerPlayersResponse](../../models/operations/getv1serverplayersresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getAdmins

Cost 2

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/admins" method="get" path="/v1/server/admins" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getAdmins();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetAdmins } from "waveshield/funcs/serverGetAdmins.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetAdmins(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetAdmins failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerAdminsResponse](../../models/operations/getv1serveradminsresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getLogs

Cost 10

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/logs" method="get" path="/v1/server/logs" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getLogs();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetLogs } from "waveshield/funcs/serverGetLogs.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetLogs(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetLogs failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1ServerLogsRequest](../../models/operations/getv1serverlogsrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerLogsResponse](../../models/operations/getv1serverlogsresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## lookupPlayer

Cost 15

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/lookup" method="post" path="/v1/server/lookup" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.lookupPlayer({
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
import { serverLookupPlayer } from "waveshield/funcs/serverLookupPlayer.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverLookupPlayer(waveShield, {
    identifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverLookupPlayer failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerLookupRequest](../../models/operations/postv1serverlookuprequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerLookupResponse](../../models/operations/postv1serverlookupresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## requestScreenshot

Cost 10

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/screenshot" method="post" path="/v1/server/screenshot" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.requestScreenshot({
    playerId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverRequestScreenshot } from "waveshield/funcs/serverRequestScreenshot.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverRequestScreenshot(waveShield, {
    playerId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverRequestScreenshot failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerScreenshotRequest](../../models/operations/postv1serverscreenshotrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerScreenshotResponse](../../models/operations/postv1serverscreenshotresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## kick

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/kick" method="post" path="/v1/server/kick" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.kick({
    playerId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverKick } from "waveshield/funcs/serverKick.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverKick(waveShield, {
    playerId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverKick failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerKickRequest](../../models/operations/postv1serverkickrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerKickResponse](../../models/operations/postv1serverkickresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getBan

Cost 2

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/server/ban" method="get" path="/v1/server/ban" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.getBan({
    banId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverGetBan } from "waveshield/funcs/serverGetBan.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverGetBan(waveShield, {
    banId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverGetBan failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1ServerBanRequest](../../models/operations/getv1serverbanrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1ServerBanResponse](../../models/operations/getv1serverbanresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## ban

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/ban" method="post" path="/v1/server/ban" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.ban({
    playerId: "<id>",
    reason: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverBan } from "waveshield/funcs/serverBan.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverBan(waveShield, {
    playerId: "<id>",
    reason: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverBan failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerBanRequest](../../models/operations/postv1serverbanrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerBanResponse](../../models/operations/postv1serverbanresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## banOffline

Cost 10

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/ban/offline" method="post" path="/v1/server/ban/offline" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.banOffline({
    reason: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverBanOffline } from "waveshield/funcs/serverBanOffline.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverBanOffline(waveShield, {
    reason: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverBanOffline failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerBanOfflineRequest](../../models/operations/postv1serverbanofflinerequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerBanOfflineResponse](../../models/operations/postv1serverbanofflineresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## unban

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/unban" method="post" path="/v1/server/unban" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.unban({
    banId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverUnban } from "waveshield/funcs/serverUnban.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverUnban(waveShield, {
    banId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverUnban failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerUnbanRequest](../../models/operations/postv1serverunbanrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerUnbanResponse](../../models/operations/postv1serverunbanresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## unbanLast

Cost 10

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/unban/last" method="post" path="/v1/server/unban/last" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.unbanLast();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverUnbanLast } from "waveshield/funcs/serverUnbanLast.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverUnbanLast(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverUnbanLast failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerUnbanLastRequest](../../models/operations/postv1serverunbanlastrequest.md)                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerUnbanLastResponse](../../models/operations/postv1serverunbanlastresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## unbanAll

Cost 50

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/unban/all" method="post" path="/v1/server/unban/all" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.unbanAll();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverUnbanAll } from "waveshield/funcs/serverUnbanAll.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverUnbanAll(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverUnbanAll failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerUnbanAllResponse](../../models/operations/postv1serverunbanallresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## executeCommand

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/exec" method="post" path="/v1/server/exec" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.executeCommand({
    command: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverExecuteCommand } from "waveshield/funcs/serverExecuteCommand.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverExecuteCommand(waveShield, {
    command: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverExecuteCommand failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerExecRequest](../../models/operations/postv1serverexecrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerExecResponse](../../models/operations/postv1serverexecresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## addAdmin

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/admin/add" method="post" path="/v1/server/admin/add" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.addAdmin({
    discordId: "<id>",
    permissions: [],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverAddAdmin } from "waveshield/funcs/serverAddAdmin.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverAddAdmin(waveShield, {
    discordId: "<id>",
    permissions: [],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverAddAdmin failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerAdminAddRequest](../../models/operations/postv1serveradminaddrequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerAdminAddResponse](../../models/operations/postv1serveradminaddresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## removeAdmin

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/server/admin/remove" method="post" path="/v1/server/admin/remove" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.server.removeAdmin({
    discordId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { serverRemoveAdmin } from "waveshield/funcs/serverRemoveAdmin.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await serverRemoveAdmin(waveShield, {
    discordId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serverRemoveAdmin failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostV1ServerAdminRemoveRequest](../../models/operations/postv1serveradminremoverequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostV1ServerAdminRemoveResponse](../../models/operations/postv1serveradminremoveresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |