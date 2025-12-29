# Bans

## Overview

Global Ban Database

### Available Operations

* [getRecent](#getrecent) - Recent Bans
* [search](#search) - Search Bans
* [getStats](#getstats) - Ban Stats
* [getTrends](#gettrends) - Ban Trends

## getRecent

Cost 2

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/bans/recent" method="get" path="/v1/bans/recent" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.bans.getRecent({});

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { bansGetRecent } from "waveshield/funcs/bansGetRecent.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await bansGetRecent(waveShield, {});
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("bansGetRecent failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1BansRecentRequest](../../models/operations/getv1bansrecentrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1BansRecentResponse](../../models/operations/getv1bansrecentresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## search

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/bans/search" method="get" path="/v1/bans/search" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.bans.search();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { bansSearch } from "waveshield/funcs/bansSearch.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await bansSearch(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("bansSearch failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1BansSearchRequest](../../models/operations/getv1banssearchrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1BansSearchResponse](../../models/operations/getv1banssearchresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getStats

Cost 5

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/bans/stats" method="get" path="/v1/bans/stats" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.bans.getStats();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { bansGetStats } from "waveshield/funcs/bansGetStats.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await bansGetStats(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("bansGetStats failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1BansStatsRequest](../../models/operations/getv1bansstatsrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1BansStatsResponse](../../models/operations/getv1bansstatsresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## getTrends

Cost 10

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/bans/trends" method="get" path="/v1/bans/trends" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.bans.getTrends();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { bansGetTrends } from "waveshield/funcs/bansGetTrends.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await bansGetTrends(waveShield);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("bansGetTrends failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetV1BansTrendsRequest](../../models/operations/getv1banstrendsrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetV1BansTrendsResponse](../../models/operations/getv1banstrendsresponse.md)\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |