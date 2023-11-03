# Install PMM Server

Percona Monitoring and Management (PMM) is an open-source platform that obliterates the complexity from database monitoring tasks. With PMM, you can effortlessly keep an eye on the performance of your database environments.

Installing PMM and monitoring a database requires 3 parts:

1. **Install PMM Server** (instructions start further below).
2. Make sure a **PMM Client is set up** and running with your database ([Link](../set-up-pmm-client/index.md)). Note: Depending on where you have your database hosted, you may have this already set up for you.
3. **Connect Database(s) to PMM Server**, so you can monitor them ([Link](../connect-databases/index.md)).

``` mermaid
graph LR
subgraph PH[PMM Host]
    PS(PMM Server)
end
subgraph DH[Database Host]
    DB[(Database)] -. Data collection .-> PC(PMM Client)
end
PC -. Data transmission .-> PS
  
```

### Requirements

Prepare your ecosystem first to ensure PMM Server can be installed without problems.

| Disk | Memory | Ports |
| - | - | - |
| :material-check-bold: 1 GB of storage per monitored database node.<br> :material-check-bold: 1 GB of storage per monitored database node for data retention set to one week. | :material-check-bold: Each database node should have at least 2 GB of memory for effective monitoring.<br> **Note:** The increase in memory usage is not proportional to the number of nodes.<br> **Example:** Data from 20 nodes should be easily handled with 16 GB. | :material-check-bold: By default, port 443 should be opened on the PMM Server.<br> :material-check-bold: The database port should be open for the PMM Agent. |

## Select where you want to run PMM Server

Select where you want to run PMM Server and follow the installation steps.

=== ":simple-docker: Docker (recommended)"

    To install PMM Server on Docker you can now opt to use our easy-install script, a fast and efficient method, or you can manually follow our steps to installing on our Docker image.
    
    [Easy-install script :material-arrow-right:](docker-easy-install.md){ .md-button .md-button--primary } [Install on a Docker Image :material-arrow-right:](docker.md){ .md-button }

=== ":simple-podman: Podman"

    Links here...

=== ":simple-helm: Helm"

    Links here...

=== ":simple-amazonaws: Amazon"

    Links here...

=== "Virtual Machine"

    Links here...