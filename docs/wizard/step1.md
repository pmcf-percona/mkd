# Step 1 of 3 — Install PMM Server

Installing the full suite of PMM, to monitor a database, requires 3 parts:

1. Installing PMM Server (instructions below)
2. Installing PMM Client on each node with a database ([Link](#))
3. Connecting PMM Client(s) → to the main PMM Server to start collecting data ([Link](#))

## Install PMM Server

### Prerequisites

Prepare your ecosystem first to ensure PMM Server4 can beinstalled without problems.

#### Disk

Approximately 1 GB of storage per monitored database node with data retention set to one week. By default, retention is 30 days.

<i info>:material-information: Useful tip:</i> Disable table statistics to decrease the VictoriaMetrics database size. [Learn more](#)

#### Memory

A minimum of 2 GB per monitored database node. The increase in memory usage is not proportional to the number of nodes. For example, data from 20 nodes should be easily handled with 16 GB.

#### Architecture

Your CPU must support the `SSE4.2` instruction set, a requirement of ClickHouse, a third-party column-oriented database used by Query Analytics. If your CPU is lacking this instruction set you won’t be able to use Query Analytics. Additionally, since PMM 2.38.0, your CPU and any virtualization layer in use must support x86-64-v2 or your container may not start.

#### Network

For PMM to work correctly, your system’s firewall should allow TCP traffic on these ports (UDP is not needed). [Learn more](#)

### Select where you want to run PMM Server

Select where you want to run PMM Server and follow the installation steps.

=== ":simple-docker: Docker (recommended)"

    To install PMM Server on Docker you can now opt to use our easy-install script, a fast and efficient method, or you can manually follow our steps to installing on our Docker image.
    
    [Easy-install script :material-arrow-right:](#){ .md-button .md-button--primary } [Install on our Docker Image :material-arrow-right:](./install-pmm-server/docker.md){ .md-button }

=== ":simple-podman: Podman"

    Links here...

=== ":simple-helm: Helm"

    Links here...

=== ":simple-amazonaws: Amazon"

    Links here...

=== "Virtual Machine"

    Links here...