# Verification Strategy

## Critical behaviors

- Full and differential modes select the appropriate input files.
- Pause and resume preserve a coherent execution state.
- Parallel jobs respect shared priority and transfer constraints.
- Progress and activity records agree with the observed job outcome.

## Test layers

| Layer | Focus |
|---|---|
| Unit | Domain rules, validation and state changes without live external dependencies. |
| Integration | Consistency across application services and their storage or external-service adapters. |
| User journey | A complete path from a user action to its visible outcome, including failure states. |

## Environment checks

Backup correctness depends on filesystem permissions, source availability and the reliability of the destination; a completed UI action must not conceal a failed transfer.
