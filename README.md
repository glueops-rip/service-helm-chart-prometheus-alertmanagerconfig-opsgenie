# prometheus-alertmanagerconfig-opsgenie

![Version: 0.1.1-alpha1](https://img.shields.io/badge/Version-0.1.1--alpha1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

This chart creates an alertmanager configuration for OpsGenie.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| labels | object | `{"alertname":"nil","component":"nil","team":"nil"}` | These labels are additional filters you can use to keep these notifications for one particular team, component, or alert. Note: you must set the same filters (with the exception of alertname) on the alert definition itself. The alert definition is also refered to as the prometheusrule. |
| opsgenie.apikey | string | `"nil"` | Leave this value as `nil` if you provided a `vault_path`. Otherwise, this value must be set. You CANNOT have a `vault_path` and `opsgenie.apikey` defined at the same time. |
| route | object | `{"groupInterval":"360m","repeatInterval":"360m"}` | Amount of time to fire an alert again after the first one is sent. |
| vault_path | string | `"nil"` | Path for to the `opsgenie_apikey` in vault. They key must be named `opsgenie_key`. The path can be anything ex. `secret/kv-v2-glueops/notifications` |
