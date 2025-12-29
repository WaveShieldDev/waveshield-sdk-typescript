# Webhooks

## Overview

Coming Soon

### Available Operations

* [list](#list) - List Active Webhooks
* [create](#create) - Create Webhook
* [delete](#delete) - Delete Webhook

## list

Coming Soon

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/v1/webhooks" method="get" path="/v1/webhooks" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  await waveShield.webhooks.list();


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { webhooksList } from "waveshield/funcs/webhooksList.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await webhooksList(waveShield);
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("webhooksList failed:", res.error);
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

**Promise\<void\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## create

Coming Soon.
Events: player_banned, player_first_time_seen


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/v1/webhooks" method="post" path="/v1/webhooks" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  await waveShield.webhooks.create();


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { webhooksCreate } from "waveshield/funcs/webhooksCreate.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await webhooksCreate(waveShield);
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("webhooksCreate failed:", res.error);
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

**Promise\<void\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |

## delete

Coming Soon

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_/v1/webhooks/{id}" method="delete" path="/v1/webhooks/{id}" -->
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  await waveShield.webhooks.delete({
    id: "<id>",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { WaveShieldCore } from "waveshield/core.js";
import { webhooksDelete } from "waveshield/funcs/webhooksDelete.js";

// Use `WaveShieldCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const waveShield = new WaveShieldCore({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const res = await webhooksDelete(waveShield, {
    id: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("webhooksDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteV1WebhooksIdRequest](../../models/operations/deletev1webhooksidrequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| errors.WaveShieldDefaultError | 4XX, 5XX                      | \*/\*                         |