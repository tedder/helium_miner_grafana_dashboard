# helium\_miner\_grafana\_dashboard

A dashboard for the Helium [miner\_exporter](https://github.com/tedder/miner_exporter) Prometheus exporter.

# Installing

Import (or copy/paste) the JSON, or **import by ID** `14319`, which uses the [grafana dashboard registry entry](https://grafana.com/grafana/dashboards/14319).

# Prometheus labels per Validator
This dashboard uses a $validator variable which assumes Prometheus metrics have a a label called "validator". The values of this label should be the short animal name of each validator. Example:
```yaml
...
  - job_name: 'validator'
    static_configs:
            - targets: ['aa.yy.zzz:1234', 'aa.yy.zzz:1235']
              labels:
                      validator: 'angry-purple-tiger'
                      network: 'testnet'
             - targets: ['bb.yy.zzz:1234', 'bb.yy.zzz:1235']
              labels:
                      validator: 'sad-dusty-yak'
                      network: 'testnet'
...
```
If you prefer to organize your prometheus config with one job per validator, you can also use the `labels` keyword under `static_config` instead of nested under `targets`
