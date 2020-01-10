# lxd-sandbox
lxd lxc containers

~~~~
sudo lxd init
sudo lxd --version

sudo lxc remote list
sudo lxc image list images
sudo lxc image list ubuntu
sudo lxc image list ubuntu-daily

sudo lxc image list images: arm64
sudo lxc image list images: arm64 ubuntu

sudo lxc init images:ubuntu/eoan/arm64 ubuntu-eoan-test-1

sudo lxc image list images: amd64
sudo lxc init images:ubuntu/eoan ubuntu-eoan-1

sudo lxc start ubuntu-eoan-1
sudo lxc stop ubuntu-eoan-1
$ sudo lxc list --format table
+---------------+---------+----------------------+------+------------+-----------+
|     NAME      |  STATE  |         IPV4         | IPV6 |    TYPE    | SNAPSHOTS |
+---------------+---------+----------------------+------+------------+-----------+
| ubuntu-eoan-1 | RUNNING | 10.36.128.212 (eth0) |      | PERSISTENT | 0         |
+---------------+---------+----------------------+------+------------+-----------+

$ sudo lxc image list
+-------+--------------+--------+--------------------------------------+---------+---------+------------------------------+
| ALIAS | FINGERPRINT  | PUBLIC |             DESCRIPTION              |  ARCH   |  SIZE   |         UPLOAD DATE          |
+-------+--------------+--------+--------------------------------------+---------+---------+------------------------------+
|       | eec75c983da9 | no     | Ubuntu eoan amd64 (20200109_07:42)   | x86_64  | 94.57MB | Jan 9, 2020 at 11:13pm (UTC) |
+-------+--------------+--------+--------------------------------------+---------+---------+------------------------------+
|       | bc1e6afb6095 | no     | Ubuntu eoan arm64 (20200109_07:59)   | aarch64 | 90.73MB | Jan 9, 2020 at 11:04pm (UTC) |
+-------+--------------+--------+--------------------------------------+---------+---------+------------------------------+
|       | daa432997875 | no     | Ubuntu xenial arm64 (20200109_07:42) | aarch64 | 73.78MB | Jan 9, 2020 at 11:09pm (UTC) |
+-------+--------------+--------+--------------------------------------+---------+---------+------------------------------+


$ sudo lxc image delete daa432997875


sudo lxc exec ubuntu-eoan-1 ping www.google.com
$ sudo lxc exec ubuntu-eoan-1 whoami
root

sudo lxc exec ubuntu-eoan-1 bash

$ sudo lxc delete ubuntu-eoan-1 --force
~~~~
