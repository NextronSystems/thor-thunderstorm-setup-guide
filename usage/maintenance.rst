Maintenance
===========

Location of the Components
--------------------------

The table below lists where THOR Thunderstorm keeps its components:

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

.. warning::
   Only restart the service if you are sure that no samples are in the queue.
   The queue will get deleted once the service restarts, so only use this if
   you are sure that no samples get lost.

Review the Service Status
-------------------------

To debug problems, run the following commands.

Check if the service is still running:

.. code-block:: console

   nextron@thunder:~$ sudo systemctl status thor-thunderstorm.service
   [sudo] password for nextron:
   ● thor-thunderstorm.service - THOR Thunderstorm Server
      Loaded: loaded (/etc/systemd/system/thor-thunderstorm.service; enabled; vendor preset: enabled)
      Active: active (running) since Wed 2023-01-18 15:28:17 CET; 17h ago
   Main PID: 39960 (thor-linux-64)

Check the last entries in the service log for errors:

.. code-block:: console

   nextron@thunder:~$ sudo tail /var/log/thunderstorm/thunderstorm.log

Check if the service is listening on a port:

.. code-block:: console

   nextron@thunder:~$ sudo ss -tlnp | grep thor

Update
------

There are two ways to update THOR Thunderstorm.

The first method will only update the signatures. This is
the safer option, since the service will not be restarted
automatically.

.. code-block:: console
   :emphasize-lines: 9

   user@unix:~$ sudo thunderstorm-update
   [...]
   Mar 21 15:54:21 unix THOR_UTIL: Info: Starting Upgrade Process
   Mar 21 15:54:21 unix THOR_UTIL: Info: License file found OWNER: user TYPE: thunderstorm STARTS: 2023/03/21 EXPIRES: 2023/03/24
   Mar 21 15:54:21 unix THOR_UTIL: Info: Downloading 'signatures'
   Mar 21 15:54:21 unix THOR_UTIL: Info: Downloading from: https://update1.nextron-systems.com/[...]
   Mar 21 15:54:21 unix THOR_UTIL: Info: already up-to-date
   Successfully updated signatures
   Now restart the Thunderstorm service at the next opportunity with: sudo systemctl restart thor-thunderstorm
   Note: Use './thunderstorm-update full' to upgrade the binaries and signatures (warning: it will also restart the service automatically)

The second method updates both the signatures and the
THOR Thunderstorm binary. This should only be used when you
are sure that the sample queue is empty and no samples are
being scanned at the moment!

.. code-block:: console
   :emphasize-lines: 14

   user@unix:~$ sudo thunderstorm-update full
   [...]
   Mar 21 15:58:47 unix THOR_UTIL: Info: Starting Upgrade Process
   Mar 21 15:58:47 unix THOR_UTIL: Info: License file found OWNER: user TYPE: thunderstorm STARTS: 2023/03/21 EXPIRES: 2023/03/24
   Mar 21 15:58:47 unix THOR_UTIL: Info: Downloading 'thor-linux'
   Mar 21 15:58:47 unix THOR_UTIL: Info: Downloading from: https://update1.nextron-systems.com/[...]
   Mar 21 15:58:48 unix THOR_UTIL: Info: already up-to-date
   Mar 21 15:58:48 unix THOR_UTIL: Info: THOR 10 detected, also updating signatures ...
   Mar 21 15:58:48 unix THOR_UTIL: Info: Starting Upgrade Process
   Mar 21 15:58:48 unix THOR_UTIL: Info: License file found OWNER: user TYPE: thunderstorm STARTS: 2023/03/21 EXPIRES: 2023/03/24
   Mar 21 15:58:48 unix THOR_UTIL: Info: Downloading 'signatures'
   Mar 21 15:58:48 unix THOR_UTIL: Info: Downloading from: https://update1.nextron-systems.com/[...]
   Mar 21 15:58:48 unix THOR_UTIL: Info: already up-to-date
   Restarting Thunderstorm service ...
   Successfully updated THOR and signatures

Replace the License
-------------------

To add a new license, copy it to the ``/etc/thunderstorm/`` directory.

The THOR Thunderstorm service automatically picks the first valid license and uses it.

.. note::
   If you've added a license with a higher quota limit (samples per hour) and the
   old one has not expired, you have to remove the old license, so that the
   Thunderstorm service cannot select and use it.
