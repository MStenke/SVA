.. _mine:

----------------------
Nutanix Mine for Veeam
----------------------

*The estimated time to complete this lab is 60 minutes.*

Overview
++++++++

This guide outlines how to deploy Mine with Veeam to an NX-cluster (including single-nodes) for demo purposes. This document should not be distributed and is for education and enablement purposes only. The changes to the respective configurations to allow single-node support are not supported production configurations.


Deploying Mine with Veeam on a Demo Cluster
+++++++++++++++++++++++++++++++++++++++++++

**Prerequisites**

1. A 1- or 4-node cluster running AOS 5.11.2.1 and AHV hypervisor
2. At least 3 free IPs (single node cluster) or 7 free IPs (four node cluster)

Resources
+++++++++
Veeam VBR NFR License: http://10.42.194.11/images/Veeam/Mine/Veeam-100instances-entplusmonitoring-nfr.lic


Procedure
+++++++++

1. Provision a new VM with the following settings:
a. vCPU – 4
b. Memory – 8GB
c. Disk 1 – Clone from Image Service – choose Veeam image
d. Add a network adapter and choose the default network
2. Save the VM
3. Power on the VM
4. Either via console or SSH, connect to the Veeam Setup VM (user is typically veeam and password veeam)
. Optional if DHCP is not configured: Set a static IP by navigating to /etc/network/interfaces, modify the line iface eth0 inet dhcp, change to the following:
a. iface eth0 inent static
b. address [IP Address]
c. netmask [Netmask]
d. gateway [Gateway]
5. sudo systemctl restart networking
6. Navigate to static IP set within a browser https://[IP]:8743

.. figure:: images/1.png

7. Login with veeam veeam then choose “Setup”

.. figure:: images/2.png

8. Accept all licenses then click Next
9. Enter Prism Element IP address

.. figure:: images/3.png

10. Enter CVM credentials (nutanix and CVM password)

.. figure:: images/4.png

11. Either upload the Windows ISO image using the Browse or use an image already uploaded to the cluster

.. figure:: images/5.png

12. Upload the license file

.. figure:: images/6.png

13. Specify IP address schema

.. figure:: images/7.png

14. Specify User name and password for the Veeam VBR Windows Server

.. figure:: images/8.png

15. Confirm the details look correct, then click “Start Install” 

.. figure:: images/9.png

16. After the deployment finishes (~2 hours) you’ll have the option to license the Windows components you can ignore this step for a demo/non-prod environment
17. You can now configure sources to backup within the Veeam B&R console. Note that if you wish to backup AHV workloads, you’ll need to deploy a Veeam Availability for Nutanix (VAN) appliance to each AHV cluster you wish to backup VMs from. Once that appliance is deployed, you configure all backup jobs and schedules for AHV from it (rather than the VBR).

