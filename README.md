# Dopt users JavaScript Node.js client

![npm sheild](https://img.shields.io/npm/v/%40dopt/users-javascript-node-client)
[![fern shield](https://img.shields.io/badge/%F0%9F%8C%BF-SDK%20generated%20by%20Fern-brightgreen)](https://buildwithfern.com/?utm_source=dopt/users-javascript-node-client/readme)

## Overview

The Dopt users JavaScript client is a friendly server-side package for identifying users and/or groups along with properties associated with them to Dopt.

It is published to npm as [`@dopt/users-javascript-node-client`](https://www.npmjs.com/package/@dopt/users-javascript-node-client).

## Installation

Via npm:

```bash
npm install @dopt/users-javascript-node-client
```

Via Yarn:

```bash
yarn add @dopt/users-javascript-node-client
```

Via pnpm:

```bash
pnpm add @dopt/users-javascript-node-client
```

## Configuration

To configure the Users JavaScript Client you will need

1. A users API key (generated in Dopt)
1. An identifier for the user or group you wish to identify (the same identifier will be used in the React SDK)
1. The properties you wish to store and/or update for the given user or group


## Usage

### Initialization

```ts
import { DoptApiClient } from '@dopt/users-javascript-node-client';

const client = new DoptApiClient({
  apiKey: process.env.DOPT_USERS_API_KEY,
});
```

### Users

Identify a single user to Dopt.

```ts
await client.users.identifyUser({
  identifier: "identifier_example",
  properties: {
    stringExample: "string",
    numberExample: 12345,
    booleanExample: true,
    nullExample: null,
  },
});
```

Identify a batch of users to Dopt.

```ts
await client.users.identifyUsers([
  {
    identifier: "identifier_example",
    properties: {
      stringExample: "string",
      numberExample: 12345,
      booleanExample: true,
      nullExample: null,
    },
  },{
    identifier: "user2_identifier",
    properties: {
      stringExample: "string",
    },
  }
]);
```

### Groups

Identify a group to Dopt.

```ts
await client.groups.identifyGroup({
  identifier: "group_identifier_example",
  properties: {
    stringExample: "string",
    numberExample: 12345,
    booleanExample: true,
    nullExample: null,
  },
})
```
