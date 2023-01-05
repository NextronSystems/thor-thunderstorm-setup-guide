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
as disk for a faster processing of queued samples.

.. list-table::
   :header-rows: 1
   :widths: 40, 30, 30

   * - Component
     - Minimum
     - Recommended
   * - CPU
     - 2 CPU Cores
     - 12+ CPU Cores
   * - Memory
     - 2 GB of RAM
     - 16 GB of RAM
   * - Disk Space (sample queue)
     - 5 GB Hard Disk Drive
     - 1 TB Solid State Drive

Network Connections
-------------------

Web UI and Sample Submission
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

HTTP(S) on port 8080/tcp (can be changed in the config)

Update Server
^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 50, 50

   * - Remote Server
     - Port
   * - update1.nextron-systems.com
     - 443/tcp
   * - update2.nextron-systems.com
     - 443/tcp

Installer
^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 50, 50

   * - Remote Server
     - Port
   * - portal.nextron-systems.com
     - 443/tcp
   * - cloud.nextron-systems.com
     - 443/tcp
