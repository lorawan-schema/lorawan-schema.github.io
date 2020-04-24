---
layout: 'home'
title: 'Welcome'
---

Welcome to the LoRaWAN Schema Definitions project page!

LoRaWAN Schema Definitions are data models and APIs used in the LoRaWAN ecosystem.

The aim of this project is to help LoRaWAN developers build interoperable solutions using schemas. The schemas are based on [JSON Schema][json-schema] and [OpenAPI][open-api] so they are usable across many different languages and frameworks.

[Read more about this project](about.md)

## Specifications

### LoRa Alliance

Specifications governed by the [LoRa Alliance][lora-alliance]:

| Mnemonic | Description | Version | Schema |
--- | --- | --- | ---
[`TS002`](ts002) | LoRaWAN Backend Interfaces | 1.0 | `https://lorawan-schema.org/ts002/1-0/schema`

### Community Contributed

Community contributed schemas can be used in future [LoRa Alliance][lora-alliance] standardization work:

| Name | Description | Version | Schema |
--- | --- | --- | ---
[`onboarding`](draft/onboarding) | Onboarding end devices and gateways | 1 | `https://lorawan-schema.org/draft/onboarding/1/schema`

## Example

Use any [JSON Schema implementation][json-schema-implementations] for validation and generation. For example, you can use [`ajv-cli`][ajv-cli] to validate a JSON document using a command-line interface.

With Node.js installed:

```bash
$ npm install -g ajv-cli
```

Download the [TS002 LoRaWAN Backend Interfaces 1.0 schema](ts002/1-0) as `schema.json`:

```bash
$ curl -o schema.json https://lorawan-schema.org/ts002/1-0/schema
```

Put the following device profile in `profile.json`:

```json
{
  "DeviceProfileID": "ExampleOTAA",
  "SupportsClassB": true,
  "ClassBTimeout": 15,
  "PingSlotFrequency": 924.5,
  "PingSlotDR": 0,
  "PingSlotPeriod": 128,
  "SupportsClassC": true,
  "ClassCTimeout": 15,
  "MACVersion": "1.0.2",
  "RegParamsRevision": "B",
  "SupportsJoin": true,
  "MaxEIRP": 14,
  "RFRegion": "US902",
  "Supports32bitFCnt": true
}
```

Validate the device profile against the schema:

```bash
$ ajv validate -s schema.json -d profile.json
```

[json-schema]: https://json-schema.org
[open-api]: https://www.openapis.org/
[lora-alliance]: https://www.lora-alliance.org
[json-schema-implementations]: https://json-schema.org/implementations.html
[ajv-cli]: https://github.com/jessedc/ajv-cli
