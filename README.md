# PageSpeed Exporter Helm Chart

This chart is based on the Helm Chart provided here: https://github.com/foomo/pagespeed_exporter/tree/master/helm/pagespeed-exporter
But this provides more options like:

- Execute the scraping via cronjobs
- Store the results using Prometheus Pushgateway

## Install

You can check the available values with the command:

```
helm repo add softonic https://charts.softonic.io 
helm show values softonic/pagespeed-exporter
```

You need to get a valid API Key from Google from this URL: https://developers.google.com/speed/docs/insights/v5/get-started

Once you have it you can use it in the chart `exporter.googleapikey`.
On other hand you just need to provide the number of targets in `exporter.targets[]`.

In case you want to make this to use the Prometheus Pushgateway you just need to define the URL `exporter.pushGatewayUrl`
and enable the cronjob with `cronjob.enabled` flag.
