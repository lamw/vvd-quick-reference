# VMware Validated Design (VVD) 4.0 Sizing Guidelines

* [Total Resources](#total-resources)
* [SDDC Infrastructure](#sddc-infrastructure)
* [SDDC Operations](#sddc-operations)
* [SDDC Automation](#sddc-automation)

## Total Resources

| Resources     | Sum                                   |
|---------------|---------------------------------------|
| Total vCPUs   | 170                                   |
| Total vRAM    | 386 GB                                |
| Total Storage | 15344 GB (vSAN 9000 GB + NFS 6344 GB) |


## SDDC Infrastructure

| VM Name               | Application                                      | Version | OS                  | vCPUS | vRAM (GB) | Storage (GB) |
|-----------------------|--------------------------------------------------|---------|---------------------|-------|-----------|--------------|
| mgmt01vc01            | vCenter Server (Management Cluster)              | 6.5a    | Virtual Appliance   | 4     | 16        | 265          |
| mgmt01psc01           | Platform Service Controller (Management Cluster) | 6.5a    | Virtual Appliance   | 2     | 4         | 114          |
| mgmt01nsxm01          | NSX Manager (Management Cluster)                 | 6.3     | Virtual Appliance   | 4     | 16        | 60           |
| comp01vc01            | vCenter Server (Resource Cluster)                | 6.5a    | Virtual Appliance   | 16    | 32        | 599          |
| comp01psc01           | Platform Service Controller (Resource Cluster)   | 6.5a    | Virtual Appliance   | 2     | 4         | 114          |
| NSX Manager           | NSX Manager (Resource Cluster)                   | 6.3     | Virtual Appliance   | 4     | 16        | 60           |
| NSX Controller #1     | NSX Controller #1                                | 6.3     | Virtual Appliance   | 4     | 4         | 20           |
| NSX Controller #2     | NSX Controller #2                                | 6.3     | Virtual Appliance   | 4     | 4         | 20           |
| NSX Controller #3     | NSX Controller #3                                | 6.3     | Virtual Appliance   | 4     | 4         | 20           |
| SFO01-MGMT-ESG01      | NSX Edge Services Gateway #1 - North-South       | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| SFO01-MGMT-ESG02      | NSX Edge Services Gateway #2 - North-South       | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| SFOMGMT-LB01-0        | NSX Edge Services Gateway #1 - oneArm LB         | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| SFOMGMT-LB01-1        | NSX Edge Services Gateway #2 - oneArm LB         | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| sfo01psc01-0          | NSX Edge Services Gateway #1 - PSC LB            | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| sfo01psc01-1          | NSX Edge Services Gateway #2 - PSC LB            | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| edge-xx-0-UDLR01-MGMT | NSX Edge Services Gateway #1 - UDLR              | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| edge-xx-1-UDLR01-MGMT | NSX Edge Services Gateway 21 - UDLR              | 6.3     | Virtual Appliance   | 2     | 1         | 1            |
| mgmt01srm01           | Site Recovery Manager                            | 6.5     | Windows Server 2012 | 2     | 4         | 40           |
| mgmt01vrms01          | vSphere Replication                              | 6.5     | Virtual Appliance   | 4     | 4         | 18           |
|                       |                                                  |         |                     |       |           |              |
|                       |                                                  |         | Total               | 66    | 116       | 1338         |

## SDDC Operations

| VM Name         | Application                                    | Version | OS                | vCPUS | vRAM (GB) | Storage (GB) |
|-----------------|------------------------------------------------|---------|-------------------|-------|-----------|--------------|
| vrops-mstrn-01  | vRealize Operations Manager - Master Node      | 6.4     | Virtual Appliance | 8     | 32        | 1048         |
| vrops-repln-02  | vRealize Operations Manager - Replica Node     | 6.4     | Virtual Appliance | 8     | 32        | 1048         |
| vrops-datan-03  | vRealize Operations Manager - Data Node        | 6.4     | Virtual Appliance | 8     | 32        | 1048         |
| vrops-rmtcol-01 | vRealize Operations Manager - Remote Collector | 6.4     | Virtual Appliance | 2     | 4         | 274          |
| vrops-rmtcol-02 | vRealize Operations Manager - Remote Collector | 6.4     | Virtual Appliance | 2     | 4         | 274          |
| vrli-mstr-01    | vRealize Log Insight - Master Node             | 4.0     | Virtual Appliance | 8     | 16        | 1332         |
| vrli-wrkr-01    | vRealize Log Insight - Worker Node             | 4.0     | Virtual Appliance | 8     | 16        | 1332         |
| vrli-wrkr-02    | NSX Controller #2                              | 4.0     | Virtual Appliance | 8     | 16        | 332          |
| mgmt01vdp01     | mgmt01vdp01                                    | 6.1.3   | Virtual Appliance | 4     | 8         | 6144         |
|                 |                                                |         |                   |       |           |              |
|                 |                                                |         | Total             | 56    | 160       | 13032        |

## SDDC Automation

| VM Name     | Application                                    | Version | OS                  | vCPUS | vRAM (GB) | Storage (GB) |
|-------------|------------------------------------------------|---------|---------------------|-------|-----------|--------------|
| vra01svr01a | vRealize Automation Appliance #1               | 7.2     | Virtual Appliance   | 4     | 18        | 140          |
| vra01svr01b | vRealize Automation Appliance #2               | 7.2     | Virtual Appliance   | 4     | 18        | 140          |
| vra01iws01a | vRealize Automation Web Server #1              | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01iws01b | vRealize Automation Web Server #2              | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01ims01a | vRealize Automation Manager Server #1          | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01ims01b | vRealize Automation Manager Server #2          | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01dem01  | vRealize Automation DEM Worker / Agent #1      | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01dem02  | vRealize Automation DEM Worker / Agent #2      | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01ias01  | vRealize Automation Proxy Agent #1             | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01ias02  | vRealize Automation Proxy Agent #2             | 7.2     | Windows Server 2012 | 2     | 4         | 60           |
| vra01bus01  | vRealize Business for Cloud Standard Server    | 7.2     | Virtual Appliance   | 4     | 8         | 50           |
| vra01buc01  | vRealize Business for Cloud Standard Collecter | 7.2     | Virtual Appliance   | 4     | 2         | 50           |
| vra01sql01  | Microsoft SQL Server 2012 (vRA & vRO DB)       |         | Windows Server 2012 | 8     | 16        | 80           |
| vra01vro01a | vRealize Orchestrator (Execution)              | 7.2     | Virtual Appliance   | 2     | 6         | 17           |
| vra01vro01b | vRealize Orchestrator (Execution)              | 7.2     | Virtual Appliance   | 2     | 6         | 17           |
|             |                                                |         |                     |       |           |              |
|             |                                                |         | Total               | 48    | 110       | 974          |