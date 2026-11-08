# CCSA104 – Security Policy Management

## Project Overview

This repository documents my practical work in Check Point Security Policy Management using SmartConsole R82 in the ICDFA Azure-hosted lab environment.

## Learning Objectives

- Understand Check Point Access Control policies.
- Inspect firewall rules and Cleanup rules.
- Manage network objects and services.
- Understand security policy sections.
- Configure and examine Hide NAT.
- Understand policy publishing and installation.
- Analyse firewall rule order and installation history.

## Lab Environment

| Component | Details |
|---|---|
| Firewall Management | Check Point SmartConsole R82 |
| Platform | ICDFA Azure-hosted environment |
| Policy Package | Standard |
| Management Server | Check Point R82 |

## Task 1 – Explore the Default Policy

### Objective
Inspect the existing Access Control policy and identify the default Cleanup rule.

### Observations

I accessed Security Policies and opened the Standard policy package. I identified the default Cleanup rule with the following visible properties:

- Rule name: Cleanup rule
- Source: Any
- Destination: Any
- Action: Drop
- Created by: System
- Expiration: Never
- Hit count: 391K (100%, Very high)

### Environment Restriction

The Standard policy package was locked for editing by another administrator session (`c44-s852`). Consequently, I could inspect the rulebase but could not safely modify its configuration.

### Inference

The Cleanup rule drops traffic that does not match an earlier applicable rule. The high hit count indicates substantial traffic has matched this rule.

### Recommendation

An authorised editing session should be made available before attempting policy modifications in the shared cloud environment.

### Evidence

Screenshots will be maintained in the `screenshots` directory.

### Learning Outcome

I gained practical exposure to the Access Control policy interface, Cleanup rule inspection and administrative session restrictions in SmartConsole R82.

---

**Documentation status:** Task 1 inspection started. Further practical activities will be documented as they are performed.
