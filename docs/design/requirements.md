# Product Requirements

A desktop backup application for creating, running and monitoring full or differential file-backup jobs through a graphical interface or command-line mode.

## Users

| Role | Expected outcome |
|---|---|
| Desktop user | Create backup jobs, launch them and inspect progress and results. |
| Advanced user | Select jobs from the command line and configure backup behavior. |

## Functional scope

| Capability | User outcome |
|---|---|
| Backup definitions | Manage named jobs with source, destination and backup mode. |
| Full and differential execution | Select between complete copying and a differential backup strategy. |
| Progress and job control | Follow execution state and control a running job. |
| Concurrent job coordination | Coordinate parallel work, file priorities and large transfers. |
| Operational safeguards | Coordinate backup activity with configured business-software constraints. |
| Logging and preferences | Record activity and expose configurable behavior and localization. |

## Main user journey

1. Define a backup job and choose its source, destination and mode.
2. Launch the selected jobs from the desktop interface or command line.
3. Monitor progress and respond to pauses or execution problems.
4. Review the recorded result and activity log.

## Acceptance priorities

- Full and differential modes select the appropriate input files.
- Pause and resume preserve a coherent execution state.
- Parallel jobs respect shared priority and transfer constraints.
- Progress and activity records agree with the observed job outcome.

## Product constraint

Backup correctness depends on filesystem permissions, source availability and the reliability of the destination; a completed UI action must not conceal a failed transfer.
