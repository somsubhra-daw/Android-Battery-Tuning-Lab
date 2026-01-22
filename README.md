# Android-Battery-Tuning-Lab

Experimental analysis of Android battery behavior using ADB, JobScheduler,
App Standby Buckets, and system power parameters.

## Motivation
Android battery drain is often blamed on apps, but system-level schedulers
and OEM policies play a major role. This repository documents controlled
experiments to understand real behavior.

## Scope
- JobScheduler quotas
- App Standby Buckets
- Wi-Fi power save behavior
- SetEdit persistence tests

## Disclaimer
Educational and research use only. Some commands may affect device stability.
Not recommended for primary devices.
