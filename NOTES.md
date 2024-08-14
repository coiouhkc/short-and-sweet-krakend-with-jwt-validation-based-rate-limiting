"telemetry/opencensus": {
    "sample_rate": 100,
    "reporting_period": 1,
    "enabled_layers": { "backend": true, "pipe": true, "router": true },
    "exporters": {
    "prometheus": {
        "port": 9090,
        "tag_host": true,
        "tag_method": true,
        "tag_path": true,
        "tag_statuscode": true
    }
    }
}

      "pluginVersion": "10.4.0",

      "pluginVersion": "11.1.3",


              "allValue": ".*",

        "datasource": {

          "type": "prometheus",

          "uid": "${DS_PROMETHEUS}"

        },

label_values(krakend_proxy_duration_bucket,http_route)

        sum(delta(http_server_duration_count{app=~"krakend", instance=~"krakend:9090", http_route=~"/mockbin"}[5m]))