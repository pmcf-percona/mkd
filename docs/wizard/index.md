# Quickstart Guide

Percona Monitoring and Management (PMM) is an open-source platform that obliterates the complexity of database performance monitoring tasks. Installing PMM and monitoring a database requires 2 parts:
{ .power-number }

1. **Install PMM Server** (instructions start further below).
2. Make sure a **PMM Client is set up** and running with your database. [Read more](./set-up-pmm-client/index.md)<br />
    <i info>Note:</i> Depending on where you have your database hosted, you may already have this step automated for you, so only minimal configuration will be required.

``` mermaid
graph LR
PS(PMM Server)
DB[(Database)] -- Data collection --> PC(PMM Client)
PC -- Transmission --> PS
  
```

## Requirements

| Disk | Memory | Ports |
| - | - | - |
| :material-check-bold: 1 GB of storage per monitored database node.<br> :material-check-bold: 1 GB of storage per monitored database node for data retention set to one week. | :material-check-bold: Each database node should have at least 2 GB of memory for effective monitoring.<br> **Note:** The increase in memory usage is not proportional to the number of nodes.<br> **Example:** Data from 20 nodes should be easily handled with 16 GB. | :material-check-bold: By default, port 443 should be opened on the PMM Server.<br> :material-check-bold: The database port should be open for the PMM Agent. |

## Select where you want to run PMM Server

=== "Bare Metal / Virtual (recommended)"

    To install **PMM Server on Docker** you can now opt to use our easy-install script, a fast and efficient method to get PMM Server running:
    
    [Easy-install script :material-arrow-right:](./install-pmm-server/docker-easy-install.md){ .md-button .md-button--primary }
    
    Alternatively, you can also install with:

    - **[Docker Image](./install-pmm-server/docker.md)** — This option is geared for those who prefer a hands-on approach, allowing you to configure PMM Server according to your preferences.
    - **[Podman](#)** — This option presents a similar containerization experience, offering a seamless setup process while ensuring isolation of your PMM Server.
    - **[Virtual Appliance](#)** — Hassle-free option that comes with all necessary components bundled together, making the setup a straightforward affair.

=== ":simple-kubernetes: Kubernetes"

    Kubernetes links here...

=== ":simple-amazonaws: Amazon"

    Amazon AWS links here...

=== ":simple-microsoftazure: Azure"

    Azure links here...

=== ":simple-googlecloud: Google Cloud"

    Google Cloud links here...
