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

#. Navigate to static IP set within a browser https://[IP]:8743

.. figure:: images/1.png

#. Login with veeam veeam then choose “Setup”

.. figure:: images/2.png

#. Accept all licenses then click Next
#. Enter Prism Element IP address

.. figure:: images/3.png

#. Enter CVM credentials (nutanix and CVM password)

.. figure:: images/4.png

#. Either upload the Windows ISO image using the Browse or use an image already uploaded to the cluster

.. figure:: images/5.png

#. Upload the license file from http://10.42.194.11/images/Veeam/Mine/Veeam-100instances-entplus-monitoring-nfr.lic

.. figure:: images/6.png

#. Specify IP address schema

.. figure:: images/7.png

#. Specify User name and password for the Veeam VBR Windows Server

.. figure:: images/8.png

#. Confirm the details look correct, then click “Start Install” 

.. figure:: images/9.png

#. After the deployment finishes (~2 hours) you’ll have the option to license the Windows components you can ignore this step for a demo/non-prod environment
#. You can now configure sources to backup within the Veeam B&R console. Note that if you wish to backup AHV workloads, you’ll need to deploy a Veeam Availability for Nutanix (VAN) appliance to each AHV cluster you wish to backup VMs from. Once that appliance is deployed, you configure all backup jobs and schedules for AHV from it (rather than the VBR).

