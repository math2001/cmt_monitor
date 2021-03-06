---
title: check_mounts
---

# Mounts

**Mounts** checks if one or more mount point in Linux filesystem are present.

## Enable the module

Enable de module in the configuration :

    # conf.yml

	Module:
  	  mount:
  	     enable: yes

## Additional parameters

This check requires additional parameters to define each mount point to be checked :

	#mount
	  mount_root:
	    module: mount
	    path: /
	  mount_mnt:
	    module: mount
	    path: /mnt


## Alerts

This check sends an alert and adds alert fields if a mount point is not present.


## Output to ElasticSearch

This module sends one message for each mount point, with the following fields:

	cmt_check: mount
	+
	cmt_mount: /path/to/mount
	cmt_mount_status: ok/nok

## CLI usage and output

	$ ./cmt.py mounts

	Check mount 
	cmt_mount              /  () 
	OK                     path / found

	Check mount 
	cmt_mount              /mnt  () 
	NOTICE                 path /mnt not found

	Check mount 
	cmt_mount              /merge  () 
	NOTICE                 path /merge not found




