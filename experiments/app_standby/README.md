# App Standby Bucket Experiment

## Test App
- Package: com.instagram.android

## Observed Bucket Transitions
- Initial reported bucket: 45 (OEM-mapped RARE)
- Subsequent reported bucket: 40 (AOSP-aligned RARE)
- After foreground usage: 10 (ACTIVE)

## Observations
- App Standby buckets are dynamically recalculated
- Foreground interaction immediately promotes apps to ACTIVE
- Forced or idle RARE classification does not persist after use
- No impact observed on kernel- or Wi-Fi-driven wakeups

## Conclusion
App Standby Buckets are effective for idle classification but are not
a reliable mechanism for addressing standby battery drain caused by
OEM or hardware-level behavior.
