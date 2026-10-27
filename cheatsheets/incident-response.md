# Incident Response Checklist

Based on the NIST SP 800-61 lifecycle.

## 1. Preparation
- [ ] Contact list and escalation path
- [ ] Logging centralized and retained
- [ ] Playbooks for common incidents (phishing, ransomware, leaked keys)

## 2. Detection and analysis
- [ ] Confirm it's a real incident, not a false positive
- [ ] Record a timeline: what, when, which systems, which accounts
- [ ] Preserve evidence (memory, disk images, logs) before changing things
- [ ] Assess scope and severity

## 3. Containment, eradication, recovery
- [ ] Short-term: isolate hosts, disable accounts, revoke keys
- [ ] Find the root cause and initial access vector
- [ ] Remove malware and persistence, patch the hole
- [ ] Restore from known-good backups; monitor closely

## 4. Post-incident activity
- [ ] Lessons-learned meeting within ~2 weeks
- [ ] Update playbooks, detections, and controls
- [ ] Write the report: timeline, impact, actions, follow-ups

## Leaked cloud key — quick playbook
1. Deactivate the key immediately
2. Check CloudTrail for everything it did
3. Delete anything the attacker created (users, roles, instances)
4. Rotate related secrets
