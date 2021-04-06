.. role:: raw-html-m2r(raw)
   :format: html

Requirements
============

Supported Operating Systems
---------------------------

* RHEL/CentOS 7 / 8
* SuSE SLES 15
* Ubuntu 18 / 20 LTS
* Debian 9 / 10

Since THOR also runs on Windows and macOS operating systems, THOR
Thunderstorm can also be used on one of these platforms but without any
support.

Hardware Requirements
---------------------

The hardware requirements highly depend on the number of samples per
minute that the service has to process.

In cases in which only a few samples per minute have to be processed,
even a dual core barebone system could be enough. However, in cases in
which thousands of samples per minute should be processed, we recommend
having a **high amount of CPU cores**, a decent amount of RAM and an SSD
as hard disk for a faster processing of queued samples.

+----------------------------------------------+----------------------------------------+
| Minimum                                      | Recommended                            |
+==============================================+========================================+
| 2 CPU Cores                                  | 12+ CPU Cores                          |
|                                              |                                        |
| 2 GB of RAM                                  | 16 GB of RAM                           |
|                                              |                                        |
| 5 GB of hard disk drive (for sample queue)   | 1 TB SSD hard drive                    |
|                                              |                                        |
|                                              | Highspeed Network Interface and Link   |
+----------------------------------------------+----------------------------------------+


Network Connections
-------------------

Web GUI and Sample Submission
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

HTTP(S) on port 8080/tcp (can be changed in config)

Update Server
^^^^^^^^^^^^^

update1.nextron-systems.com 443/tcp

update2.nextron-systems.com 443/tcp

Installer
^^^^^^^^^

portal.nextron-systems.com 443/tcp

cloud.nextron-systems.com 443/tcp
