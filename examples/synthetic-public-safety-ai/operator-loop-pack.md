# Synthetic Public Safety Operator Loop Pack

## Scenario

A public-safety inspection team needs a tighter loop for field inspections of recurring safety hazards in small commercial buildings.

## Minimum Viable Loop Fragment

- **Trigger input**: inspector starts a scheduled inspection for one building type
- **AI judgment / transformation**: AI suggests the most likely checklist branch and drafts issue descriptions from field notes
- **Action / routing**: inspector reviews the draft, confirms the issue, and routes it into the inspection record
- **Human confirmation**: inspector must confirm every hazard record before it is written
- **Output / write-back**: structured hazard record in the existing inspection system
- **Feedback / verification**: supervisor spot-checks accepted records against evidence
- **Archive / audit**: photos, timestamps, checklist branch, and confirmation decision are retained
- **Fallback mode**: manual checklist entry with no AI draft

## Case Replay Fragment

### Ugly Case

- **Operator involved**: field inspector
- **Decision point**: whether an obstructed exit counts as a recordable hazard
- **Action taken**: inspector takes a photo but delays the decision until after the visit
- **Evidence available at the time**: photo, site note, building type context
- **Outcome**: the issue is entered late and the handoff to review is inconsistent
- **What this case proves**: the real bottleneck is not seeing the exit but turning evidence into a timely structured record
- **What this case does not prove**: that a broader autonomous enforcement loop is needed

## Eval Pack Fragment

- **Evaluation objective**: verify that in-scope hazard records are drafted accurately enough to reduce inspector documentation time without weakening review quality
- **Golden cases**: clear blocked exit, missing extinguisher signage, obvious corridor obstruction
- **Failure cases**: non-hazard clutter, duplicate photo from same issue, note with no visible hazard
- **Edge cases**: poor lighting, partially obstructed view, mixed-use corridor
- **Ambiguous cases**: temporary obstruction during delivery, incomplete sign visibility
- **Acceptance threshold**: reviewer accepts or lightly edits the AI draft on at least 80 percent of in-scope cases
- **Demo-killing cases**: repeated false hazard drafts on normal conditions
- **Review owner**: inspection supervisor

## Governance And Risk Overlay Fragment

- **AI authority level**: advisory with gated write support
- **Advisory surfaces**: checklist branch suggestion, hazard draft description
- **Gated action surfaces**: record creation after inspector confirmation
- **Write-capable surfaces**: structured draft stored only after human confirmation
- **Human confirmation points**: every hazard record, every route to escalation
- **Audit trail**: prompt inputs, draft output, inspector confirmation, attached evidence
- **Rollback condition**: revert to manual record entry if reviewers reject too many drafts or if audit gaps appear
- **Risk owner**: inspection program lead
- **Known unacceptable failure modes**: unconfirmed hazards written as final records, missing evidence on accepted records

## Day-2 Operations Fragment

- **Operating owner**: inspection operations lead
- **Exception owner**: regional review supervisor
- **Monitoring signals**: draft acceptance rate, review turnaround time, missing-evidence count
- **Drift or degradation signal**: increasing reviewer overrides or repeated false hazard drafts for the same building type
- **Manual fallback mode**: inspectors enter records manually with the standard checklist
- **Review cadence**: weekly review of pilot records
- **Operator adoption signal**: inspectors continue using the draft flow without side-channel note taking
- **Asset promotion candidate**: reusable public-safety inspection eval starter pack
