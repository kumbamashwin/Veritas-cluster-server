# Details of the veritas cluster server

### clusters an Types of clusters
### Jeopardy
### Split brain Condition
### LLT
##### VCS uses two components LLT and GAB to share the data over the private networks between two nodes. LLT is Low tatency transport provides fast kernel to kernel communication between the nodes.
  - These components will provide the performance and reliability required by the cluster.
  # LLT
  - LLT provides fast kernel to kernel communications and monitors network connections between nodes in the cluster
  - System admin creates LLT configuration file called llttab which describes the systems in the cluster and private communication links betwwne them. LLT runs in the level 2 of the network stack.
### GAB
- GAB group membershio and atomic broadcast provides the network communications and group membership
- GAB will form the synhronization among the nodes by establishng the heartbeat links, the system admin will configure GAB driver by creating a configuration file called gabtab
### Service Groups
- Service groups can be defined as containers which will be containing all kinds of resources which are used for running of a application.
- failover or swithover happens over the Service groups, service groups will go unhealthy or shows error when any resources or their dependencies fails or have error
### Resources
- Resources are the software or hardware components which needs to be run up and running to constitute a application.
- Every resource will have a agent which will monitor the resource and gives the status to the cluster
  
# Basic commands 

### Service Group 

#### Make the vcs configuration read write
```
haconf -makerw 
```
#### Add a service group with Name sg-name
```
hagrp -add sg-name
```
#### Modify service group, and stating in which systems it has to be available and giving the system priorities
```
hagrp -modify sg-name SystemList system1 1 system2 2 
```
#### autoenabling the service group sg-name on the system system1 
```
hagrp -autoenable sg-name -sys system1
```
#### Making the configuration of the cluster readonly
```
haconf -dump -makero
```
### Resoucres 

#### Create a resource 
```
hares -add resource-name
```
