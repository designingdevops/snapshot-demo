## Snapshot Disks

This demo shows an example of how you can use Azure DevOps Pipelines to snapshot
disks in resource groups.

In this example you will need a service connection in Azure DevOps that has access to 
the resource groups you want to create snapshots in as well as access to the disks you 
want to snapshot.  By default the snapshots are created in the same resource group as 
the source disk but this can be changed by using the -t parameter.  

Also to run this unattended in a pipeline you will need to use the -i flag or else
the program will prompt you before it continues.

The pipeline reads in a file called resource-groups.txt.  This file provides the input
for the snapshot programming.  It should have one resource group per line.  Each line
of this file will be processed and disks in that resource group will have snapshots created.

There is currently a schedule on the pipeline that executes it daily at midnight.  It can also
be executed manually in ADO.

NOTE:  This is provided as example code and not tested for production use.
