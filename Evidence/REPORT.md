# p2-14-helpdesk — GREEN

Django 5.2.12 → 6.0.4. Source django-helpdesk/django-helpdesk @ 5c2808dec2ba3b63d107b715d7d5b326feda666f.
Preregistration: https://github.com/j4groupfounders/j4-upgrades-harness/commit/6cf87daccde1910714fe47fd0c9b552f9302fae1
Baseline: dab36aedbffa5e2ec5650c117e06c98a4a52e766; upgraded: f1990354ab0e882b41a030738790d969eea4c1f3.

- Project tests: **464 passed, 2 pre-existing skips** before and after; exact collected IDs/skips match: True. No removed/newly skipped tests. Helpdesk subtests additionally retained by original assertions.
- Boot/HTTP: five fixed real-server GET snapshots match: True; model fixture snapshots match: True. No unexplained drift or framework behavior exception.
- Independent seeded faults: project-only **5/5**, combined **5/5**. One fresh-checkout matrix job per mutation, no build state shared. Combined miss-rate halving: True.
- **5 workflow runs**, **6.15 actual job-minutes**, including screening failures and all five matrix jobs. Cap 12. Standard public Ubuntu runners, $0 paid API/service calls. Session token cost is not exposed/measured.
- Zero human app/test edits. Permanent agent app/test logic edits: zero (only the preregistered temporary fault injections). Framework upgrade only changes two pinned dependency files; exact diff preserved as upgrade.patch.

## Repairs and limits
Third screening run repaired harness-only serialization: convert the lazy-translated unassigned label to str before JSON. No app/test logic changed.
Harness baseline HTTP boot settings use disposable SQLite, DEBUG=False, local-only allowed hosts and in-memory email. Original app/test source untouched. Original upstream workflows replaced on pilot branches with bounded verification; no upstream modifications/contact.
These are three new Django applications, not three new stacks. Current upstream already advertises compatible framework ranges, so the result supports controlled dependency-upgrade compatibility, not arbitrary legacy migration success.
HTTP remains empty-DB unauthenticated; model probes use fixed unsaved objects. Todo's old due-date fixture is not full clock freezing. Wiki's 3 opt-in browser tests and Helpdesk's 2 upstream skipped attachment tests remain skipped. No authenticated frozen HTTP replay, full route/line coverage, external integrations or production certification.
Seed targets are preregistered measured business/permission surfaces; not an unbiased whole-app mutation score. The extra model checks catch faults beyond the project's suite where applicable.

## Evidence runs
- [37620123732](https://github.com/j4groupfounders/j4-p2e-helpdesk/actions/runs/37620123732) — j4/p2e-baseline, success, 0.72 job-min
- [37620446403](https://github.com/j4groupfounders/j4-p2e-helpdesk/actions/runs/37620446403) — j4/p2e-baseline, failure, 0.75 job-min
- [37620674426](https://github.com/j4groupfounders/j4-p2e-helpdesk/actions/runs/37620674426) — j4/p2e-baseline, success, 0.55 job-min
- [37621133967](https://github.com/j4groupfounders/j4-p2e-helpdesk/actions/runs/37621133967) — j4/p2e-upgrade, success, 0.62 job-min
- [37621367422](https://github.com/j4groupfounders/j4-p2e-helpdesk/actions/runs/37621367422) — j4/p2e-seeds, success, 3.52 job-min

## Seed detections

```json
[
  {
    "mutation": 0,
    "tests": 466,
    "skipped": 2,
    "project_detected": true,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 1,
    "tests": 466,
    "skipped": 2,
    "project_detected": true,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 2,
    "tests": 466,
    "skipped": 2,
    "project_detected": true,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 3,
    "tests": 466,
    "skipped": 2,
    "project_detected": true,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 4,
    "tests": 466,
    "skipped": 2,
    "project_detected": true,
    "harness_detected": true,
    "combined": true
  }
]
```
