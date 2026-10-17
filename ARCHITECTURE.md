# EasySave — Backup Job Manager — Architecture

Users define source and destination locations, choose a backup mode and follow the execution of their jobs. The project combines a desktop interface with a backup engine, progress tracking, logging and coordination rules for concurrent transfers.

## Components

| Component | Responsibility |
|---|---|
| Desktop views | Avalonia screens for job creation, execution and preferences. |
| View models | MVVM state and commands for user interactions. |
| Backup engine | Job orchestration, file selection and transfer execution. |
| Coordination services | Priority, large-file and business-software coordination. |
| Persistence and logging | Job configuration, execution state and activity records. |
| Platform adapters | Filesystem access and operating-system-dependent behavior. |

## Main interactions

```mermaid
flowchart TD
    N0["Desktop interface"]
    N1["View models"]
    N2["Command-line selection"]
    N3["Job services"]
    N4["Backup execution engine"]
    N5["Filesystem adapters"]
    N6["Progress and activity records"]
    N0 --> N1
    N2 --> N3
    N1 --> N3
    N3 --> N4
    N4 --> N5
    N4 --> N6
```

## Responsibility boundaries

- Use MVVM for the desktop interface. UI state and commands can be tested separately from the visual controls.
- Separate file selection from copying. Full and differential behavior can share the execution infrastructure.
- Coordinate shared transfer constraints centrally. Parallel jobs can honor common priority and resource rules.

## Constraints

Backup correctness depends on filesystem permissions, source availability and the reliability of the destination; a completed UI action must not conceal a failed transfer.

## Technology

C#/.NET, Avalonia, MVVM, JSON/XML logging and automated .NET tests.
