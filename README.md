opensuse-base-docker
====================

Kiwi build files for opensuse 13.2 base image for Docker

Refer To:

  - [openSUSE-KIWI Image System: Cookbook](http://doc.opensuse.org/projects/kiwi/doc/#chap.lxc)
  - [Flavio Castelli Blog](http://flavio.castelli.name/2013/04/12/docker-and-opensuse)


The recipe:

  - Do you have KIWI installed? see Flavio's Blog

  - Pull these files to your computer

		$ git clone https://github.com/stephen-marshall-moore/opensuse-base-docker.git opensuse-base-docker

  - Create rootfs of the container:

		$ sudo /usr/bin/kiwi --prepare ./opensuse-base-docker --root /tmp/openSUSE_13_2_base_rootfs

  - Roll the result into a tarball:

		$ sudo tar cvjpf openSUSE_13_2_base.tar.bz2 -C /tmp/openSUSE_13_2_base_rootfs/ .

  - Import into docker:

		$ cat openSUSE_13_2_base.tar.bz2 | docker import - nimbostrati/opensuse_13_2_base

