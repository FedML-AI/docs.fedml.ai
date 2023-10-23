---
sidebar_position: 3
---
# Device Management - fedml device

## Overview
```
Usage: fedml device bind [OPTIONS] [API_KEY].

Options:
  -v, --version TEXT  Bind to which backend environment version of FedML® Nexus
                      AI Platform. It should be dev, test, or release.
  -c, --compute_node  Bind as the general compute node in FEDML Nexus AI
                      compute network. This is enabled by default. After
                      binding, you can view and manage the device in the FEDML®
                      Nexus AI Platform: https://nexus.fedml.ai/compute. It
                      can be grouped as a cluster and then you can use
                      FEDML®Launch to schedule any job (training, deployment,
                      federated learning) to it. You can not specify the
                      option -c and -s simultaneously.
  -s, --server        Bind as the FedML on-premise parameter server (PS). It
                      can be used for PS-based training paradigms, such as
                      distributed training, cross-cloud training, and
                      federated-learning. You can not specify the option -c
                      and -s simultaneously for a single environment.
  -p, --provider      Bind as the FedML compute node (GPU) provider
                      (supplier). This is used by Nexus AI Platform - Share
                      and Earn: https://nexus.fedml.ai/gpu-supplier. You can
                      share your GPUs in this way and earn money. You can
                      specify the option -p and -c simultaneously (can be used
                      as provider for others as well compute node for your own
                      jobs), but you can not specify -p and -s simultaneously.
```

## Options {#options-1}

| Name                  | Default   | Description                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `--version` or `-v`   | `release` | Bind to which backend environment version of FedML® Nexus AI Platform. It should be dev, test, or release.                                                                                                                                                                                                                                                                                                        |
| `--computing` or `-c` | `true`    | Bind as the general compute node in FEDML Nexus AI compute network. This is enabled by default. After binding, you can view and manage the device in the FEDML® Nexus AI Platform: https://nexus.fedml.ai/compute. It can be grouped as a cluster and then you can use FEDML®Launch to schedule any job (training, deployment,federated learning) to it. You can not specify the option -c and -s simultaneously. |
| `--server` or `-s`    | `false`   | Bind as the FedML on-premise parameter server (PS). It can be used for PS-based training paradigms, such as distributed training, cross-cloud training, and federated-learning. You can not specify the option -c and -s simultaneously for a single environment.                                                                                                                                                 |
| `--provider` or `-p`  | `false`   | Bind as the FedML compute node (GPU) provider (supplier). This is used by Nexus AI Platform - Share and Earn: https://nexus.fedml.ai/gpu-supplier. You can share your GPUs in this way and earn money. You can specify the option -p and -c simultaneously (can be used as provider for others as well compute node for your own jobs), but you can not specify -p and -s simultaneously.                         |

## Arguments {#argument-1}
| Name                  | Default                    | Description                                                                                                        |
|-----------------------|----------------------------|--------------------------------------------------------------------------------------------------------------------|
| `API_KEY`             | required, no default value | You can find your API Key at https://nexus.fedml.ai. Click your avatar on top-right area and then click "Profile". |

## Examples {#example-1}

Bind as a general compute node in FEDML Nexus AI Cloud:
```
fedml device bind <API_KEY>
```

Bind as a federated-learning server in FEDML Nexus AI Cloud:
```
fedml device bind -s <API_KEY>
```

Bind as the compute node (GPU) provider (supplier) in FEDML Nexus AI Cloud:
```
fedml device bind -p <API_KEY>
```

# Unbind from the FedML® Nexus AI Platform

## Overview
```
Usage: fedml device unbind [OPTIONS]

Options:
  -c, --compute_node  Unbind from the FedML general compute node.
  -s, --server        Unbind from the the FedML on-premise parameter server (PS).
  -v, --version TEXT  Unbind which backend environment version of FedML® Nexus
                      AI Platform. It should be dev, test, or release.
```


## Options {#options-2}

| Name                     | Default   | Description                                                                                               |
|--------------------------|-----------|-----------------------------------------------------------------------------------------------------------|
| `--compute_node` or `-c` | `true`    | Unbind from the FedML general compute node.                                                               |
| `--server` or `-s`       | `false`   | Unbind from the the FedML on-premise parameter server (PS).                                               |
| `--version` or `-v`      | `release` | Unbind which backend environment version of FedML® Nexus AI Platform. It should be dev, test, or release. |

## Examples {#example-2}

Unbind from a general compute node in FEDML Nexus AI Cloud:
```
fedml device unbind -c
```

Unbind from a federated-learning server in FEDML Nexus AI Cloud:
```
fedml device unbind -s
```