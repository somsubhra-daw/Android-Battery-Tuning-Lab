# Android-Battery-Tuning-Lab

A research-focused repository documenting controlled experiments on
Android battery behavior using system-level tools such as ADB,
JobScheduler, App Standby Buckets, and power-related global settings.

This project focuses on **observation, measurement, and documentation** —
not battery-boosting claims or unsafe tweaks.

---

## Motivation

Battery drain on Android devices is often attributed to applications,
but real-world behavior is heavily influenced by:
- System schedulers
- Background execution quotas
- OEM-specific power management policies

This lab aims to understand **what actually happens** when these systems
are modified, based on experiments rather than assumptions.

---

## Scope of Experiments

- JobScheduler quota controller analysis
- App Standby Bucket behavior
- Wi-Fi power save timing and impact
- Persistence of system settings (ADB / SetEdit)
- OEM-specific deviations from AOSP behavior

---

## Repository Structure

adb/ → ADB commands and rollback guides
experiments/ → Controlled battery experiments
├── job_scheduler/
├── app_standby/
└── wifi_power/
metrics/ → Batterystats and drain analysis
setedit/ → SetEdit-related observations
oem-notes/ → OEM-specific behavior notes
   


---

## Methodology

1. Establish a clean baseline using `dumpsys batterystats`
2. Change **one variable at a time**
3. Observe behavior over realistic usage periods
4. Record both improvements and regressions
5. Always provide rollback instructions

No experiment is considered valid without:
- Baseline comparison
- Measurable impact
- Side-effect analysis

---

## Safety & Ethics

- Educational and research use only
- Some commands modify global system settings
- Not recommended for primary or production devices
- OEM implementations may override or ignore AOSP defaults

Users are expected to understand the risks before applying any changes.

---

## Key Takeaways (Evolving)

- Battery optimization is highly OEM-dependent
- Aggressive tuning often causes hidden regressions
- Many popular “battery tweaks” have negligible real impact

This section will evolve as experiments are completed.

---

## Disclaimer

This repository does **not** provide battery-boosting tools, apps, or
guaranteed optimizations.  
All findings are observational and device-specific.

---

## Status

🧪 Active research project  
📱 Primary test device: Motorola (Android-based)

Contributions, discussions, and reproducible experiments are welcome.


