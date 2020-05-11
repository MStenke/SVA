.. _mine:

----------------------
Nutanix Mine for Veeam
----------------------

Overview
++++++++

This guide outlines how to deploy Mine with Veeam to an NX-cluster for demo purposes.


Deploying Mine with Veeam on a Demo Cluster
+++++++++++++++++++++++++++++++++++++++++++

1. Navigate to **Nutanix Mine with Veeam Foundation VM** within a browser https://[IP]:8743

.. figure:: images/1.png

2. Login with veeam veeam then choose “Setup”

.. figure:: images/2.png

3. Accept all licenses then click Next

4. Enter Prism Element IP address, username and password

.. figure:: images/3.png

5. Enter CVM credentials (nutanix and CVM password)

.. figure:: images/4.png

6. Either upload the Windows ISO image using the Browse or use an image already uploaded to the cluster

.. figure:: images/5.png

7. Upload the license file from http://10.42.194.11/images/Veeam/Mine/Veeam-100instances-entplus-monitoring-nfr.lic

.. figure:: images/6.png

8. Specify IP address schema

.. figure:: images/7.png

9. Specify User name and password for the Veeam VBR Windows Server

.. figure:: images/8.png

10. Confirm the details look correct, then click “Start Install” 

.. figure:: images/9.png

11. After the deployment finishes (~2 hours) you’ll have the option to license the Windows components you can ignore this step for a demo/non-prod environment
12. You can now configure sources to backup within the Veeam B&R console. Note that if you wish to backup AHV workloads, you’ll need to deploy a Veeam Availability for Nutanix (VAN) appliance to each AHV cluster you wish to backup VMs from. Once that appliance is deployed, you configure all backup jobs and schedules for AHV from it (rather than the VBR).

