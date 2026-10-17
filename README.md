# EasySave — Backup Job Manager

A desktop backup application for creating, running and monitoring full or differential file-backup jobs through a graphical interface or command-line mode.

Users define source and destination locations, choose a backup mode and follow the execution of their jobs. The project combines a desktop interface with a backup engine, progress tracking, logging and coordination rules for concurrent transfers.

## Users

| Role | Use |
|---|---|
| Desktop user | Create backup jobs, launch them and inspect progress and results. |
| Advanced user | Select jobs from the command line and configure backup behavior. |

## Main features

- **Backup definitions.** Manage named jobs with source, destination and backup mode.
- **Full and differential execution.** Select between complete copying and a differential backup strategy.
- **Progress and job control.** Follow execution state and control a running job.
- **Concurrent job coordination.** Coordinate parallel work, file priorities and large transfers.
- **Operational safeguards.** Coordinate backup activity with configured business-software constraints.
- **Logging and preferences.** Record activity and expose configurable behavior and localization.

## Typical workflow

1. Define a backup job and choose its source, destination and mode.
2. Launch the selected jobs from the desktop interface or command line.
3. Monitor progress and respond to pauses or execution problems.
4. Review the recorded result and activity log.

## Project structure

```text
easysave-public-version/
├── .github/
│   └── workflows/
├── application/
│   ├── cli/
│   ├── models/
│   │   ├── backup/
│   │   │   ├── abstractions/
│   │   │   ├── coordination/
│   │   │   ├── entities/
│   │   │   ├── execution/
│   │   │   ├── io/
│   │   │   ├── runtime/
│   │   │   ├── selection/
│   │   │   ├── services/
│   │   │   └── shared/
│   │   ├── businesssoftware/
│   │   ├── data/
│   │   │   ├── configuration/
│   │   │   └── persistence/
│   │   ├── logger/
│   │   ├── state/
│   │   └── utils/
│   ├── viewmodels/
│   │   └── services/
│   ├── views/
│   │   └── styles/
│   └── Program.cs
├── docs/
│   ├── design/
│   │   ├── decisions.md
│   │   ├── requirements.md
│   │   └── verification.md
│   └── uml/
├── logging/
├── logging-tests/
├── server/
│   └── model/
├── tests/
├── tools/
│   └── module-001/
│       └── Program.cs
├── translations/
├── ARCHITECTURE.md
└── README.md
```

[Complete directory structure](docs/design/structure.md)

| Area | Responsibility |
|---|---|
| Desktop views | Avalonia screens for job creation, execution and preferences. |
| View models | MVVM state and commands for user interactions. |
| Backup engine | Job orchestration, file selection and transfer execution. |
| Coordination services | Priority, large-file and business-software coordination. |
| Persistence and logging | Job configuration, execution state and activity records. |
| Platform adapters | Filesystem access and operating-system-dependent behavior. |

## Technology

C#/.NET, Avalonia, MVVM, JSON/XML logging and automated .NET tests.

## Engineering

- [Architecture](ARCHITECTURE.md)
- [Product requirements](docs/design/requirements.md)
- [Design decisions](docs/design/decisions.md)
- [Verification strategy](docs/design/verification.md)

Backup correctness depends on filesystem permissions, source availability and the reliability of the destination; a completed UI action must not conceal a failed transfer.

---

Source code, operational configuration and project-specific data are withheld for confidentiality.
