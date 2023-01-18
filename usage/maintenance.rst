Maintenance
===========

Location of the Components
--------------------------

Config:           /etc/thunderstorm/thunderstorm.yml
Binaries & Sigs:  /opt/nextron/thunderstorm
Logs:             /var/log/thunderstorm (you can change that in the configuration)
Sample Files:     /tmp/thunderstorm (you can change that in the configuration)

Restart the Service
-------------------

.. code-block:: console 

   systemctl stop thor-thunderstorm
   systemctl start thor-thunderstorm

.. code-block:: console 

   systemctl restart thor-thunderstorm

Review the Service Status
-------------------------

Check if the service is still running

.. code-block:: console 

   systemctl status thor-thunderstorm

Check the last entries in the service log for errors

.. code-block:: console 

   tail /var/log/thunderstorm/thunderstorm.log

Check if the service listens on a port 

.. code-block:: console 

   netstat -anpt | grep thor

Replace the License
-------------------

In order to add a new license, copy it to the ``/etc/thunderstorm`` folder. 

The THOR Thunderstorm service will automatically pick the first valid license and use it. 

If you've added a license with a higher quota limit (samples per hour) and the old one has not expired, you have to remove the old license so that the Thunderstorm service cannot select and use it.
