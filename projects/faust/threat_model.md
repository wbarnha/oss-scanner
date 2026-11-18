# Threat model

## What this project does and where untrusted input enters

Faust is a Python stream-processing library for Kafka-based applications. Treat message keys, values, headers, serialized records, and broker responses as untrusted input. Application configuration and data passed through Faust's command-line and processing APIs can also affect its behavior.

## Components that matter most / least

The message decoding and serialization paths, stream and table processing, transport integration, and configuration handling are in scope. Security issues in optional third-party services or dependencies themselves are out of scope; Faust's handling of their input and output remains in scope.

## How to exercise it

Use the unit, functional, integration, meticulous, and regression tests in `tests/`. The project README documents `./scripts/install` and `./scripts/tests` for local development.

## How you rate severity

Assess impact in the context of a Faust application processing attacker-controlled messages. Consider confidentiality, integrity, and availability, and include the preconditions and demonstrated impact. Do not report ordinary application-level errors or malformed input handling without a security impact.
