==============
Updating (IoT)
==============

Due to the complexity of the :abbr:`IoT (Internet of Things)` box and virtual Windows :abbr:`IoT
(Internet of Things)` box , the term 'updating' can mean several different things. The actual
drivers can be updated, the core code on the :abbr:`IoT (Internet of Things)` box can be updated
and, lastly a new image can be flashed (physical :abbr:`IoT (Internet of Things)` box). This
document will explore the various ways to update the :abbr:`IoT (Internet of Things)` box to ensure
smooth operation of :abbr:`IoT (Internet of Things)` box processes and devices.

Handlers (drivers) update
=========================

There may be some instances where the drivers or interfaces need to be updated for individual
devices (e.g. scale, measurement tools, etc.). The IoT handlers (drivers and interfaces) code can be
modified by syncing them with the configured server handler's code. This can be helpful in instances
where :abbr:`IoT (Internet of Things)` devices (e.g. scales, measurement tools, etc.) are not
working properly with the :abbr:`IoT (Internet of Things)` box.

For both the Windows :abbr:`IoT (Internet of Things)` (Odoo 16 and higher) and physical :abbr:`IoT
(Internet of Things)` box, this process can be performed manually from the :abbr:`IoT (Internet of
Things)` box homepage. Go to the :abbr:`IoT (Internet of Things)` box homepage by navigating to
:menuselection:`IoT app --> IoT Boxes` and clicking on the :guilabel:`IP address` of the :abbr:`IoT
(Internet of Things)` box.

Next, click :guilabel:`Handlers list` and then select :guilabel:`Load Handlers` at the bottom of the
page.

.. image:: updating_iot/load-handlers.png
   :align: center
   :alt: Handlers list on an IoT box with the load handlers button highlighted.

.. important::
   Handlers code is fetched from the configured server and it needs to be up-to-date to have the
   latest fixes and patches. See :ref:`upgrade/homepage_upgrade`.

.. note::
   The handlers update is also performed automatically each time the :abbr:`IoT (Internet of
   Things)` box is restarted. The only exception to this process is if the :guilabel:`Automatic
   drivers update` is unchecked in the form view of the :abbr:`IoT (Internet of Things)` box on the
   Odoo server. This setting can be reached by going to :menuselection:`IoT App --> Select the IoT
   box --> Automatic drivers update`.

.. _upgrade/homepage_upgrade:

Update from the IoT box home page
=================================

.. important::
   This update does not apply to the Windows :abbr:`IoT (Internet of Things)` box (Odoo 16 and
   higher). To update the Windows :abbr:`IoT (Internet of Things)`, first, uninstall the previous
   version of the Odoo Windows program and then reinstall it, with the most up-to-date installation
   package. To begin the installation, navigate to the Odoo 16 or higher installation package for
   Enterprise or Community - Windows edition at `Odoo’s download page <https://odoo.com/download>`_.

In the background, the :abbr:`IoT (Internet of Things)` box uses a version of Odoo code to run and
connect to the Odoo database. This code may need to be updated in order for the :abbr:`IoT (Internet
of Things)` box to operate effectively. This operation should be completed on a routine basis, to
ensure up-to-date :abbr:`IoT (Internet of Things)` processes and core system.

Go to the :abbr:`IoT (Internet of Things)` box homepage by navigating to :menuselection:`IoT app -->
IoT Boxes` and clicking on the :guilabel:`IP address` of the :abbr:`IoT (Internet of Things)` box.
Then click on :guilabel:`Update` (next to the version number).

If a new version of the :abbr:`IoT (Internet of Things)` Box image is available, an
:guilabel:`Upgrade to _xx.xx_` button will appear at the bottom of the page. Click this button to
upgrade the unit and the :abbr:`IoT (Internet of Things)` box will then flash itself to the new
version. All of the previous configurations will be saved.

.. note::
   This process can take more than 30 minutes. Do not turn off or unplug the :abbr:`IoT (Internet of
   Things)` box as it would leave it in an inconsistent state. This means that the :abbr:`IoT
   (Internet of Things)` box will need to be re-flashed with a new image.

   .. seealso::
      :ref:`flash_sdcard/etcher`.

.. important::
   An :guilabel:`Upgrade` button will appear if the :abbr:`IoT (Internet of Things)` box is on the
   latest image. In this case, the :abbr:`IoT (Internet of Things)` box will instead update the core
   code (without changing the image itself). In other words this button forces Odoo based :abbr:`IoT
   (Internet of Things)` box code to update with the latest version from GitHub. This can be done
   **without** an Odoo database to synchronize with. The Upgrade button will show only if the
   :abbr:`IoT (Internet of Things)` box is on the latest image. The :abbr:`IoT (Internet of Things)`
   box may need to be re-flashed to the latest image first to perform this upgrade. See
   :ref:`flash_sdcard/etcher`.

.. image:: updating_iot/flash-upgrade.png
   :align: center
   :alt: IoT box software upgrade in the IoT Box Home Page.

.. _flash_sdcard/etcher:

Flashing the SD card on IoT box
===============================

.. important::
   This update does not apply to the Windows :abbr:`IoT (Internet of Things)` box (Odoo 16 and
   higher). To update the Windows :abbr:`IoT (Internet of Things)`, first, uninstall the previous
   version of the Odoo Windows program and then reinstall it, with the most up-to-date installation
   package. To begin the installation, navigate to the Odoo 16 or higher installation package for
   Enterprise or Community - Windows edition at `Odoo’s download page <https://odoo.com/download>`_.

In some circumstances, the :abbr:`IoT (Internet of Things)` box's micro SD Card may need to be
re-flashed with Etcher software to benefit from Odoo's latest :abbr:`IoT (Internet of Things)` image
update. This means that the Odoo :abbr:`IoT (Internet of Things)` box software may need to be
updated in instances of a new :abbr:`IoT (Internet of Things)` box, or when a handlers update and
update from the :abbr:`IoT (Internet of Things)` box home page does not fix issues.

.. warning::
   It is often imperative to re-flash the :abbr:`IoT (Internet of Things)` box's image after
   upgrading the Odoo database to a new version.

.. note::
   A computer with a micro SD card reader/adapter is required to re-flash the micro SD card.

Navigate to Balena's website and download `Etcher <https://www.balena.io/>`_. It is a free and
open source utility used for burning image files onto drives. Click to `download
<https://www.balena.io/etcher#download-etcher>`_. Install and launch the program on the computer.

Then download the latest IoT image from `nightly <http://nightly.odoo.com/master/iotbox/>`_ :
`iotbox-latest.zip`

This image is compatible with all supported versions of Odoo.

The images should be downloaded and extracted to a convenient file location.

After this step is complete, insert the :abbr:`IoT (Internet of Things)` box's micro SD card into
the computer or reader. Open *Etcher* and select :guilabel:`Flash from file`, then find and select
the image just downloaded and extracted. Next, select the drive the image should be burned to.
Lastly, click on :guilabel:`Flash` and wait for the process to finish.

.. image:: updating_iot/etcher-app.png
   :align: center
   :alt: Balena's Etcher software dashboard.

.. tip::
   Balena's Etcher software also allows for the administrator to flash the :abbr:`SD (Secure
   Digital)` SD card from an :abbr:`URL (Uniform Resource Locator)`. To flash from an :abbr:`URL
   (Uniform Resource Locator)`, simply click :guilabel:`Flash from URL` instead of :guilabel:`Flash
   from file`.

   .. image:: updating_iot/url-flash.png
      :align: center
      :alt:  A view of Balena's Etcher software, with the flash from URL option highlighted.

.. note::
   An alternative software for flashing the micro SD card is *Raspberry Pi Imager*. Download the
   *Raspberry Pi* software `here <https://www.raspberrypi.com/software/>`_.
