# Design Decisions

## 1. Use MVVM for the desktop interface

**Benefit.** UI state and commands can be tested separately from the visual controls.

**Trade-off.** View-model responsibilities must remain distinct from transfer orchestration.

## 2. Separate file selection from copying

**Benefit.** Full and differential behavior can share the execution infrastructure.

**Trade-off.** Each selection mode requires its own correctness checks.

## 3. Coordinate shared transfer constraints centrally

**Benefit.** Parallel jobs can honor common priority and resource rules.

**Trade-off.** Coordination adds interaction cases across otherwise independent jobs.
