.. include:: global.rst
.. issues:

Common Issues
=============

.. _fleaissue:

My Flea market doesn't have new offeres or trades?
--------------------------------------------------

.. note:: 
   This issue can be caused by a misconfigured ``coopConfig.json`` file. It stops the flea market requests from coming through correctly
   which stops new offeres and trades from appearing. Here are the steps to fix it.

#. Stop the AKI Server
#. Open the ``coopConfig.json`` located in ``SIT\Server\user\mods\SITCoop\config\``
#. Change "messageWSUrlOverride:" to your local IP with the ``:6969`` port at the end (Your Local IP should go 192.168.X.X)
#. Change "useMessageWSUrlOverride:" to "true" **MAKE SURE TRUE IS LOWERCASE**
#. Save the file and reboot the server and make sure it's working

I'm getting an ``ERROR: listen EADDRNOTAVAIL: address not avalible`` error.
---------------------------------------------------------------------------

.. note:: 
   This happens because there is already a process running that is taking up the target port, and multiple apps can't access the same port
   below is a quick command line method to find what is currently holding the port and close it

#. Press ``Win + R`` and enter "cmd"
#. Press ``CTRL + Shift + Enter`` to open cmd as an admin, click "Yes" to allow
#. Type ``netstat -ano | findstr : 6969``
#. There should be a set of numbers at the end of the process, like ``17720``
#. Type ``taskkill /PID (NUMBER) /F``, replace (NUMBER) with the number you got from above and hit enter
#. Try booting your server again

Infinite loading screen
-----------------------

.. note:: 
   If you are getting an infinite loading screen, this is usually caused by mods that aren't compatible with the current version of |SIT|, try remvoing all your mods
   and launching the game and server again.

SIT Manager "A task was cancelled"
----------------------------------

.. note:: 
   This is most often caused by a firewall issue, however it can also be caused by an incorrect IP address

   Make sure you have entered the hosts IPv4 address correctly, and if using a VPN that there isn't any connection issues between you and the host.

Aki.Server.exe Has Deleted itself
---------------------------------

.. note:: 
   For some reason windows defender is dectecting the Aki server as malware, this is a false postive, Aki have requested it not be flagged as malware, however this
   process can take more than a month to resolve, so in the meantime, add the server directory as an exeption to Windows Defender, like below:

   (You will read Click 10 times, and you **WILL** enjoy it)

#. Open windows settings
#. Click "Update and Security"
#. Click "Windows Security"
#. Click "Open Windows Security"
#. Click "Virus and Threat Protection"
#. Under "Virus & Threat protection settings" click "Manage Settings"
#. Scroll down to "Exclusions" and click "Add or Remove exclusions"
#. Click "Add an Exclusion" and click "Folder"
#. Navigate to your |SDIR| and click "Select Folder"

.. raw:: html

   <details>
      <summary>Firewall Exclusion</summary>

.. video:: _static/videos/WindowsFirewall.webm
   :width: 700
   :loop:

.. raw:: html

   </details>

|brs|
