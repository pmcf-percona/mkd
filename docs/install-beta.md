# Product Beta quickstart guides

Peroduct Beta (PB) is an open-source database monitoring, management, and observability solution for MySQL, PostgreSQL, and MongoDB.

To install PB there are three stages to complete: set up **PB Server**, set up **at least one PB Client**, and then add the **database service(s)**. 

You can select from multiple easy-to-follow installation options, depending on your project's structure, but **we recommend using Docker** for a convenient and quick way to set it up.

=== ":simple-docker: Docker"

    Using our Docker image is the most convenient way to run PB Server and PB Client as a preconfigured Docker container on Linux or MacOS.

    Check below to get access to a detailed step-by-step guide.

    [View Docker Guide :material-arrow-right:](test2.md){ .md-button }

=== ":simple-windowsterminal: Package Manager"

    If you're on **Ubuntu** or **Debian**, use `apt` for convenience.
    
    On the other hand, if you're on **Red Hat Enterprise Linux** or **CentOS**, you can easily use `yum`.
    
    Choose your package manager below to get access to a detailed step-by-step guide.

    [Install via `apt` :material-arrow-right:](test.md){ .md-button } [Install via `yum` :material-arrow-right:](#){ .md-button }

=== ":simple-kubernetes: Kubernetes"

    **Percona Operators** are controllers introduced to simplify complex deployments that require meticulous and secure database expertise.
    
    Check below to get access to a detailed step-by-step guide.

    [View Kubernetes Guide :material-arrow-right:](test.md){ .md-button }

=== ":octicons-download-16:  Manual Installation"

    If you prefer to start with a specific version or implement it offline, check out the link below for a step-by-step guide and get access to the downloads directory.

    [View Manual Installation Guide :material-arrow-right:](test.md){ .md-button }

--8<-- "services-banner.md"