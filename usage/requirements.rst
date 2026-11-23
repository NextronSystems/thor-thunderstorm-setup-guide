Requirements
============

Supported Operating Systems
---------------------------

The following operating system versions are the minimum requirements for
THOR Thunderstorm:

* RHEL 7
* CentOS 7
* SUSE SLES 15
* Ubuntu 18
* Debian 9

License Requirements
--------------------

A valid service license is needed to use THOR Thunderstorm. Please see
:ref:`usage/install-thunderstorm-service:get a service license` for more
information.

Hardware Requirements
---------------------

The hardware requirements depend heavily on the number of samples per
minute that the service has to process.

In cases in which only a few samples per minute have to be processed,
even a dual-core system could be enough. However, in cases in
which thousands of samples per minute should be processed, we recommend
having a **high number of CPU cores**, a decent amount of RAM and an SSD
for faster processing of queued samples.

.. list-table::
   :header-rows: 1

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

For a detailed and up-to-date list of our update and licensing
servers, please visit https://www.nextron-systems.com/resources/hosts/.

Web UI and Sample Submission
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The THOR Thunderstorm service listens on port 8080/tcp.
You can change the port in the configuration.
You can also use HTTPS for the service. Please see
the chapter :ref:`usage/next-steps:configuration`.

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
