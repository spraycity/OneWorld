# ADR 0001: Offline-first product architecture

- Status: Accepted as project direction; implementation pending
- Date: 2026-11-26

## Context
The mission requires equitable access and strong privacy. Dependence on paid inference APIs would create recurring cost and network barriers.

## Decision
Design the production core to run locally after model installation. Optional network-assisted modes may be considered only when explicitly enabled and clearly separated from offline mode.

## Consequences
- larger downloads and local hardware requirements;
- device/browser compatibility work;
- model licensing and update integrity become critical;
- offline quality and latency must be benchmarked honestly.
