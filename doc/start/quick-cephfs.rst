=====================
 Ceph FS Quick Start
=====================

.. important:: **We do not recommend using Ceph FS in a production environment yet.**  RBD, ``librbd``, RADOS, ``librados`` and RADOS Gateway are production ready.

To mount the Ceph FS filesystem, you must have a running Ceph cluster. You may 
execute this quick start on a separate host if you have the Ceph packages and 
the ``/etc/ceph/ceph.conf`` file installed with the appropriate IP address
and host name settings modified in the ``/etc/ceph/ceph.conf`` file.

.. important:: Mount the Ceph FS file system on a separate host from your Ceph cluster.

Kernel Driver
=============

Mount Ceph FS as a kernel driver. :: 

	sudo mkdir /mnt/mycephfs
	sudo mount -t ceph {ip-address-of-monitor}:6789:/ /mnt/mycephfs
	
Filesystem in User Space (FUSE)
===============================

Mount Ceph FS as with FUSE. Replace {username} with your username. ::

	sudo mkdir /home/{username}/cephfs
	sudo ceph-fuse -m {ip-address-of-monitor}:6789 /home/{username}/cephfs
