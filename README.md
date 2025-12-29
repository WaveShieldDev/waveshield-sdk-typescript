# waveshield

Developer-friendly & type-safe Typescript SDK specifically catered to leverage *waveshield* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=waveshield&utm_campaign=typescript)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/waveshield/api). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

WaveShield API: Official API documentation for the WaveShield Anti-Cheat System and its network tools.

## Authentication
All API endpoints require authentication using API Keys.
headers:
- `x-api-key`: Your public Access Key
- `x-api-secret`: Your private Secret Key

## Rate Limiting & Cost
- Limits are applied per minute based on your API Key tier.
- Each endpoint has a cost associated with it. Your API Key tier determines your monthly quota.
- Response headers `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset`, `X-Cost` included.
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [waveshield](#waveshield)
  * [Authentication](#authentication)
  * [Rate Limiting & Cost](#rate-limiting-cost)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication-1)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add waveshield
```

### PNPM

```bash
pnpm add waveshield
```

### Bun

```bash
bun add waveshield
```

### Yarn

```bash
yarn add waveshield
```

> [!NOTE]
> This package is published with CommonJS and ES Modules (ESM) support.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

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

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security schemes globally:

| Name            | Type   | Scheme  | Environment Variable         |
| --------------- | ------ | ------- | ---------------------------- |
| `apiKeyAuth`    | apiKey | API key | `WAVESHIELD_API_KEY_AUTH`    |
| `apiSecretAuth` | apiKey | API key | `WAVESHIELD_API_SECRET_AUTH` |

You can set the security parameters through the `security` optional parameter when initializing the SDK client instance. The selected scheme will be used by default to authenticate with the API for all operations that support it. For example:
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
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [Auth](docs/sdks/auth/README.md)

* [verify](docs/sdks/auth/README.md#verify) - Verify API Credentials

### [Bans](docs/sdks/bans/README.md)

* [getRecent](docs/sdks/bans/README.md#getrecent) - Recent Bans
* [search](docs/sdks/bans/README.md#search) - Search Bans
* [getStats](docs/sdks/bans/README.md#getstats) - Ban Stats
* [getTrends](docs/sdks/bans/README.md#gettrends) - Ban Trends

### [Keys](docs/sdks/keys/README.md)

* [getUsage](docs/sdks/keys/README.md#getusage) - Get Usage Stats

### [Player](docs/sdks/player/README.md)

* [search](docs/sdks/player/README.md#search) - Search Players
* [get](docs/sdks/player/README.md#get) - Player Profile
* [getServers](docs/sdks/player/README.md#getservers) - Server History
* [getBans](docs/sdks/player/README.md#getbans) - Player Active Bans
* [getBansHistory](docs/sdks/player/README.md#getbanshistory) - Player Ban History
* [getThreatScore](docs/sdks/player/README.md#getthreatscore) - Threat Score
* [analyze](docs/sdks/player/README.md#analyze) - Player Analysis
* [discordLookup](docs/sdks/player/README.md#discordlookup) - Discord Lookup

### [Server](docs/sdks/server/README.md)

* [getInfo](docs/sdks/server/README.md#getinfo) - Server Info
* [getStats](docs/sdks/server/README.md#getstats) - Server Statistics
* [getBans](docs/sdks/server/README.md#getbans) - Server Active Bans
* [getBanHistory](docs/sdks/server/README.md#getbanhistory) - Server Ban History
* [getConfig](docs/sdks/server/README.md#getconfig) - Server Config
* [getPlayers](docs/sdks/server/README.md#getplayers) - Online Players List
* [getAdmins](docs/sdks/server/README.md#getadmins) - Server Admins
* [getLogs](docs/sdks/server/README.md#getlogs) - Server Logs
* [lookupPlayer](docs/sdks/server/README.md#lookupplayer) - Lookup Player
* [requestScreenshot](docs/sdks/server/README.md#requestscreenshot) - Request Screenshot
* [kick](docs/sdks/server/README.md#kick) - Kick Player
* [getBan](docs/sdks/server/README.md#getban) - Get Ban Info
* [ban](docs/sdks/server/README.md#ban) - Ban Player
* [banOffline](docs/sdks/server/README.md#banoffline) - Ban Player Offline
* [unban](docs/sdks/server/README.md#unban) - Unban Player
* [unbanLast](docs/sdks/server/README.md#unbanlast) - Unban Last Players
* [unbanAll](docs/sdks/server/README.md#unbanall) - Unban All Players
* [executeCommand](docs/sdks/server/README.md#executecommand) - Execute Console Command
* [addAdmin](docs/sdks/server/README.md#addadmin) - Add Admin
* [removeAdmin](docs/sdks/server/README.md#removeadmin) - Remove Admin

### [Stats](docs/sdks/stats/README.md)

* [get](docs/sdks/stats/README.md#get) - Global System Stats

### [Webhooks](docs/sdks/webhooks/README.md)

* [list](docs/sdks/webhooks/README.md#list) - List Active Webhooks
* [create](docs/sdks/webhooks/README.md#create) - Create Webhook
* [delete](docs/sdks/webhooks/README.md#delete) - Delete Webhook

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`authVerify`](docs/sdks/auth/README.md#verify) - Verify API Credentials
- [`bansGetRecent`](docs/sdks/bans/README.md#getrecent) - Recent Bans
- [`bansGetStats`](docs/sdks/bans/README.md#getstats) - Ban Stats
- [`bansGetTrends`](docs/sdks/bans/README.md#gettrends) - Ban Trends
- [`bansSearch`](docs/sdks/bans/README.md#search) - Search Bans
- [`keysGetUsage`](docs/sdks/keys/README.md#getusage) - Get Usage Stats
- [`playerAnalyze`](docs/sdks/player/README.md#analyze) - Player Analysis
- [`playerDiscordLookup`](docs/sdks/player/README.md#discordlookup) - Discord Lookup
- [`playerGet`](docs/sdks/player/README.md#get) - Player Profile
- [`playerGetBans`](docs/sdks/player/README.md#getbans) - Player Active Bans
- [`playerGetBansHistory`](docs/sdks/player/README.md#getbanshistory) - Player Ban History
- [`playerGetServers`](docs/sdks/player/README.md#getservers) - Server History
- [`playerGetThreatScore`](docs/sdks/player/README.md#getthreatscore) - Threat Score
- [`playerSearch`](docs/sdks/player/README.md#search) - Search Players
- [`serverAddAdmin`](docs/sdks/server/README.md#addadmin) - Add Admin
- [`serverBan`](docs/sdks/server/README.md#ban) - Ban Player
- [`serverBanOffline`](docs/sdks/server/README.md#banoffline) - Ban Player Offline
- [`serverExecuteCommand`](docs/sdks/server/README.md#executecommand) - Execute Console Command
- [`serverGetAdmins`](docs/sdks/server/README.md#getadmins) - Server Admins
- [`serverGetBan`](docs/sdks/server/README.md#getban) - Get Ban Info
- [`serverGetBanHistory`](docs/sdks/server/README.md#getbanhistory) - Server Ban History
- [`serverGetBans`](docs/sdks/server/README.md#getbans) - Server Active Bans
- [`serverGetConfig`](docs/sdks/server/README.md#getconfig) - Server Config
- [`serverGetInfo`](docs/sdks/server/README.md#getinfo) - Server Info
- [`serverGetLogs`](docs/sdks/server/README.md#getlogs) - Server Logs
- [`serverGetPlayers`](docs/sdks/server/README.md#getplayers) - Online Players List
- [`serverGetStats`](docs/sdks/server/README.md#getstats) - Server Statistics
- [`serverKick`](docs/sdks/server/README.md#kick) - Kick Player
- [`serverLookupPlayer`](docs/sdks/server/README.md#lookupplayer) - Lookup Player
- [`serverRemoveAdmin`](docs/sdks/server/README.md#removeadmin) - Remove Admin
- [`serverRequestScreenshot`](docs/sdks/server/README.md#requestscreenshot) - Request Screenshot
- [`serverUnban`](docs/sdks/server/README.md#unban) - Unban Player
- [`serverUnbanAll`](docs/sdks/server/README.md#unbanall) - Unban All Players
- [`serverUnbanLast`](docs/sdks/server/README.md#unbanlast) - Unban Last Players
- [`statsGet`](docs/sdks/stats/README.md#get) - Global System Stats
- [`webhooksCreate`](docs/sdks/webhooks/README.md#create) - Create Webhook
- [`webhooksDelete`](docs/sdks/webhooks/README.md#delete) - Delete Webhook
- [`webhooksList`](docs/sdks/webhooks/README.md#list) - List Active Webhooks

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  const result = await waveShield.auth.verify({
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
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
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`WaveShieldError`](./src/models/errors/waveshielderror.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                            |
| ------------------- | ---------- | ------------------------------------------------------ |
| `error.message`     | `string`   | Error message                                          |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                     |
| `error.headers`     | `Headers`  | HTTP response headers                                  |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned. |
| `error.rawResponse` | `Response` | Raw HTTP response                                      |

### Example
```typescript
import { WaveShield } from "waveshield";
import * as errors from "waveshield/models/errors";

const waveShield = new WaveShield({
  security: {
    apiKeyAuth: process.env["WAVESHIELD_API_KEY_AUTH"] ?? "",
    apiSecretAuth: process.env["WAVESHIELD_API_SECRET_AUTH"] ?? "",
  },
});

async function run() {
  try {
    const result = await waveShield.auth.verify();

    console.log(result);
  } catch (error) {
    if (error instanceof errors.WaveShieldError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);
    }
  }
}

run();

```

### Error Classes
**Primary error:**
* [`WaveShieldError`](./src/models/errors/waveshielderror.ts): The base class for HTTP error responses.

<details><summary>Less common errors (6)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/httpclienterrors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/httpclienterrors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/httpclienterrors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/httpclienterrors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/httpclienterrors.ts): Unrecognised or unexpected error.


**Inherit from [`WaveShieldError`](./src/models/errors/waveshielderror.ts)**:
* [`ResponseValidationError`](./src/models/errors/responsevalidationerror.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `serverURL: string` optional parameter when initializing the SDK client instance. For example:
```typescript
import { WaveShield } from "waveshield";

const waveShield = new WaveShield({
  serverURL: "https://api.waveshield.xyz",
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
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to use the `"beforeRequest"` hook to to add a
custom header and a timeout to requests and how to use the `"requestError"` hook
to log errors:

```typescript
import { WaveShield } from "waveshield";
import { HTTPClient } from "waveshield/lib/http";

const httpClient = new HTTPClient({
  // fetcher takes a function that has the same signature as native `fetch`.
  fetcher: (request) => {
    return fetch(request);
  }
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new WaveShield({ httpClient: httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { WaveShield } from "waveshield";

const sdk = new WaveShield({ debugLogger: console });
```

You can also enable a default debug logger by setting an environment variable `WAVESHIELD_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=waveshield&utm_campaign=typescript)
