---
title: influx pkg
description: The 'influx pkg' command and its subcommands manage InfluxDB templates.
menu:
  v2_0_ref:
    name: influx pkg
    parent: influx
weight: 101
v2.0/tags: [templates]
related:
  - /v2.0/influxdb-templates/use/
---

The `influx pkg` command manages InfluxDB templates.
_For information about finding and using InfluxDB templates, see
[Use InfluxDB templates](/v2.0/influxdb-templates/use/)._

## Usage
```
influx pkg [flags]
influx pkg [command]
```

## Subcommands
| Subcommand                                           | Description                      |
|:-------                                              |:-----------                      |
| [export](/v2.0/reference/cli/influx/pkg/export/)     | Export resources as a template   |
| [stack](/v2.0/reference/cli/influx/pkg/stack/)       | Manage stacks                    |
| [summary](/v2.0/reference/cli/influx/pkg/summary/)   | Summarize the specified template |
| [validate](/v2.0/reference/cli/influx/pkg/validate/) | Validate the specified template  |

## Flags

| Flag                      | Description                                                                                 | Input Type | {{< cli/mapped >}} |
|:----                      |:-----------------------------                                                               |:---------- |:------------------ |
| `-c`, `--disable-color`   | Disable color in output                                                                     |            |                    |
| `--disable-table-borders` | Disable table borders                                                                       |            |                    |
| `-e`, `--encoding`        | Encoding of the input stream                                                                | string     |                    |
| `--env-ref`               | Environment references to provide with the template (format: `--env-ref=REF_KEY=REF_VALUE`) | string     |                    |
| `-f`, `--file`            | Path to template file                                                                       | string     |                    |
| `--force`                 | Ignore warnings about destructive changes                                                   |            |                    |
| `-h`, `--help`            | Help for the `pkg` command                                                                  |            |                    |
| `-o`, `--org`             | Organization name that owns the bucket                                                      | string     | `INFLUX_ORG`       |
| `--org-id`                | Organization ID that owns the bucket                                                        | string     | `INFLUX_ORG_ID`    |
| `-q`, `--quiet`           | Disable output printing                                                                     |            |                    |
| `-R`, `--recurse`         | Recurse through files in the directory specified in `-f`, `--file`                          |            |                    |
| `--secret`                | Secrets to provide with the template (format: `--secret=SECRET_KEY=SECRET_VALUE`)           | string     |                    |
| `-u`, `--url`             | URL of template file                                                                        | string     |                    |

{{% cli/influx-global-flags %}}
