# Wi-Fi Power Experiment

## Configuration
- wifi_power_save = 120
- Network: Stable Wi-Fi connection
- Screen state: Mostly OFF
- Power saver: OFF

## Observations
- WLAN_CE_2 wakeups persisted during device idle
- qcom_rx_wakelock remained active despite power save hint
- No significant reduction in Wi-Fi-driven wake frequency
- Connectivity remained stable (no major reconnect issues)

## Conclusion
The global wifi_power_save setting did not significantly reduce
Wi-Fi-driven idle wakeups on this device. Results indicate that
standby drain is governed primarily by Qualcomm Wi-Fi firmware
and OEM kernel behavior rather than Android framework-level controls.
