Maintenance
===========

Location of the Components
--------------------------

THOR Thunderstorm uses several components and paths for the configuration.
Please see the table below for more information:

.. list-table:: 
   :header-rows: 1
   :widths: 30, 70

   * - Component
     - Path
   * - Config
     - /etc/thunderstorm/thunderstorm.yml
   * - Binaries & Signatures
     - /opt/nextron/thunderstorm
   * - Logs
     - /var/log/thunderstorm (you can change that in the configuration)
   * - Sample Files
     - /tmp/thunderstorm (you can change that in the configuration)

Restart the Service
-------------------

The following command will restart the THOR Thunderstorm service:

.. code-block:: console 

   nextron@thunder:~$ sudo systemctl restart thor-thunderstorm.service

Review the Service Status
-------------------------

To debug potential problems, you can run the following commands and
see what might be the problem.

Check if the service is still running:

.. code-block:: console 

   nextron@thunder:~$ sudo systemctl status thor-thunderstorm.service
   [sudo] password for nextron:
   ● thor-thunderstorm.service - THOR Thunderstorm Server
      Loaded: loaded (/etc/systemd/system/thor-thunderstorm.service; enabled; vendor preset: enabled)
      Active: active (running) since Wed 2023-01-18 15:28:17 CET; 17h ago
   Main PID: 39960 (thor-linux-64)

Check the last entries in the service log for errors

.. code-block:: console 

   nextron@thunder:~$ tail /var/log/thunderstorm/thunderstorm.log

Check if the service is listening on a port:

.. code-block:: console 

   nextron@thunder:~$ sudo netstat -anpt | grep thor

Replace the License
-------------------

In order to add a new license, copy it to the ``/etc/thunderstorm/`` directory. 

The THOR Thunderstorm service will automatically pick the first valid license and use it. 

If you've added a license with a higher quota limit (samples per hour) and the old one has
not expired, you have to remove the old license so that the Thunderstorm service cannot select and use it.
