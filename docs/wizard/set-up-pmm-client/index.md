# Set up PMM Client

To make Percona Monitoring and Management (PMM) work properly a **PMM Client** needs to be set up in your database environment. This client acts as the messenger, relaying back the key performance insights from your database to the PMM Server.

Up next, we'll walk you through the installation steps to set up PMM Client.

Please select your database technology below.

## Select your database location

Select where your database is located so you can choose the best way to set up a PMM Client alongside your database and collect data signals back to PMM Server.

=== ":material-server-network: Self-hosted/EC2"

    Opting for a self-hosted, be it bare-metal, virtual machine, etc., or even for an Amazon EC2 setup gives you a more hands-on control over your environment, making it a go-to choice for those who prefer a more personalized setup.

    **Using Percona Repositories (Recommended)** — a streamlined setup process, with the added assurance that you're always using the latest, tested, and supported version.
    
    [Install using Percona Repositories :material-arrow-right:](percona-repositories.md){ .md-button .md-button--primary }

    **Install on a Docker image** — A convenient way to run PMM Client as a preconfigured Docker container.
    
    [Install on a Docker image :material-arrow-right:](#){ .md-button }

    **Manual Installation** — By downloading the files you can install at your pace and even in an environment with restricted internet access.
    
    [Manual Installation :material-arrow-right:](#){ .md-button }

=== ":simple-amazonaws: RDS/Aurora"

    Links here...

=== ":material-google-cloud: Google Cloud"

    Links here...

=== ":simple-microsoftazure: Azure"

    Links here...

=== ":material-help-network: Other"

    Links here...