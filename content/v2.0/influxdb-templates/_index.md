---
title: InfluxDB templates
description: >
  InfluxDB templates are prepackaged InfluxDB configurations that contain everything
  from dashboards and Telegraf configurations to notifications and alerts.
menu: v2_0
weight: 9
v2.0/tags: [templates]
---

InfluxDB templates are prepackaged InfluxDB configurations that contain everything
from dashboards and Telegraf configurations to notifications and alerts.
Use InfluxDB templates to quickly set up a fresh instance of InfluxDB, back up your
dashboard configuration, or share your configuration with the InfluxData community.

## Template manifests
A template is defined in a single file known as a **manifest**.
Template manifests support the following formats:

- [YAML](https://yaml.org/)
- [JSON](https://www.json.org/)
- [Jsonnet](https://jsonnet.org/)

{{% note %}}
Template manifests are compatible with
[Kubernetes Custom Resource Definitions (CRD)](https://kubernetes.io/docs/tasks/access-kubernetes-api/custom-resources/custom-resource-definitions/).
{{% /note %}}

_See [Create an InfluxDB template](/v2.0/influxdb-templates/create/) for information about
generating template manifests._

### Template resources
Include the following **resources** in a template:

- buckets
- checks
- dashboards
- dashboard variables
- labels
- notification endpoints
- notification rules
- tasks
- Telegraf configurations

---

{{< children >}}
