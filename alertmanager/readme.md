# Prometheus and Alertmanager Setup Guide

## Overview
Alerting with Prometheus involves:
1. Setting up and configuring Alertmanager.
2. Configuring Prometheus to communicate with Alertmanager.
3. Creating alerting rules in Prometheus.

## 1. Setup and Configure Alertmanager

### Alertmanager Configuration (`alertmanager.yml`)
Update the configuration file with your email details for alert notifications. Follow the [Google Support](https://support.google.com/mail/answer/185833?hl=en) link to create an app password.

```yaml
global:
  resolve_timeout: 5m

route:
  receiver: 'Mail Alert'
  group_by: [ alertname ]
  repeat_interval: 30s
  group_wait: 15s
  group_interval: 15s

receivers:
  - name: 'Mail Alert'
    email_configs:
      - smarthost: smtp.gmail.com:587
        auth_username: 'your-email-id@gmail.com'
        auth_password: 'xxxx xxxx xxxx xxxx'
        from: 'your-email-id@gmail.com'
        to: 'receiver-email-id@gmail.com'
        headers:
          subject: 'Prometheus Mail Alerts'

inhibit_rules:
  - source_match:
      severity: 'critical'
    target_match:
      severity: 'warning'
    equal: ['alertname', 'dev', 'instance']
```

For more alerting rules, visit [Awesome Prometheus Alerts](https://samber.github.io/awesome-prometheus-alerts/).
