# JobScheduler Quota Experiment

## Objective
To study how Android JobScheduler quota limits affect background job
execution frequency and battery drain.

## Device & Environment
- Device: Motorola (model unspecified)
- Android version: (fill this)
- Network: Wi-Fi + Mobile Data
- Test duration: 24 hours per run
- Usage pattern: Normal daily usage

## Baseline
Default JobScheduler quota values were recorded before applying any
custom configuration.

Command used:
```
adb shell settings get global job_scheduler_quota_controller_constants
```

## Experiment Setup
A conservative quota configuration was applied to reduce excessive
background job execution without breaking app functionality.

Command applied:
```
adb shell settings put global job_scheduler_quota_controller_constants
max_job_count_per_rate_limiting_window=10,rate_limiting_window_ms=60000
```

## Metrics Collected
- Screen-off battery drain (%/hour)
- Background job execution count
- Notification delivery delay (if any)
- User-visible side effects

## Observations
## Analysis (Test 1)

With conservative JobScheduler quota limits applied, background jobs
executed in more grouped bursts rather than frequent isolated wakeups.

Notification delivery and system services remained functional, indicating
no major regressions from this configuration.

However, standby wakeups attributed to WLAN-related wake reasons
(e.g., WLAN_CE_2, qcom_rx_wakelock) persisted, confirming that these
are outside the scope of JobScheduler control.

This experiment demonstrates that JobScheduler tuning can improve
scheduler behavior but cannot resolve kernel or driver-level power issues.
## Rollback
To restore default behavior:
```
adb shell settings delete global job_scheduler_quota_controller_constants
```

## Notes
Results may vary across OEMs due to additional background execution
policies.

