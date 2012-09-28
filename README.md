OS-Folsom-qos-patches
=====================

Patches for easier set_qos in Cinder and CinderClient Folsom release of OpenStack

This repo includes two git patches that add the ability to set IOPs based QoS on volumes.

Changes include additional columns in DataBase, set_qos(min_iops, max_iops, burst_iops) methods,
and of course and update to the SolidFire driver to implement this.

This is implemented as an extension in the Cinder OS-API.

python-cinderclient includes an addition to volumes class to add set_qos() method.

NOTE:
=====
This patch is derived from git 'format-patch master' on branch that was submitted based on Folsom release.

To Apply patch:
==============
First verify the changes in the patches:
.. git apply --stat cinder-folsom_set_qos.patch
.. git apply --stat cinderclient-folsom_set_qos.patch

To test the patches:
.. git apply --check cinder-folsom_set_qos.patch
.. git apply --check cinderclient-folsom_set_qos.patch

To apply the patches using git am:
.. git am --signoff < cinder-folsom_set_qos.patch
.. git am --signoff < cinderclient-folsom_set_qos.patch
