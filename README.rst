=================================
 Repo Manifests for LEDE Projects
=================================

Google Repo manifests to ease cloning and checking out all of the projects for
LEDE and OpenWRT.

LEDE Information
================

Docs:

* https://lede-project.org/docs/guide-developer/the-source-code

Git repos:

* https://git.lede-project.org/

Projects on above site:

+------------------------------------------------------+------------------------------------+
| Git Repo URI                                         | Description                        |
+======================================================+====================================+
| git://git.lede-project.org/source.git                | LEDE Source Repository             |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/feed/packages.git         | Feed Packages                      |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/firewall3.git     | OpenWrt firewall configuration...  |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/fstools.git       | OpenWrt filesystem utilities       |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/iwinfo.git        | Library for accessing wireless...  |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/jsonpath.git      | JSON parsing utility               |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/librpc-uclibc.git | Standalone librpc forked from...   |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/libubox.git       | C utility functions for OpenWrt    |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/luci.git          | Lua Configuration Interface...     |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/luci2/ui.git      | LuCI2 UI modules                   |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/make_ext4fs.git   | Standalone fork of Android...      |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/mdnsd.git         | OpenWrt MDNS daemon                |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/mountd.git        | OpenWrt automount daemon           |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/netifd.git        | OpenWrt Network interface...       |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/odhcp6c.git       | OpenWrt DHCPv6 Client              |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/odhcpd.git        | OpenWrt DHCP Server                |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/procd.git         | OpenWrt service / process...       |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/relayd.git        | IPv4 pseudo-bridge routing...      |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/rpcd.git          | OpenWrt ubus RPC daemon            |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/ubox.git          | OpenWrt core utilities             |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/ubus.git          | OpenWrt system message/RPC bus     |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/uci.git           | OpenWrt Unified Configuration...   |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/uclient.git       | libubox HTTP client library        |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/ugps.git          | OpenWrt GPS daemon                 |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/uhttpd.git        | Tiny HTTP server                   |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/umbim.git         | OpenWrt MBIM modem utility         |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/uqmi.git          | Tiny QMI command line utility      |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/usbmode.git       | usbmode - usb_modeswitch repla...  |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/usign.git         | Tiny signify replacement           |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/ustream-ssl.git   | ustream SSL wrapper                |
+------------------------------------------------------+------------------------------------+
| git://git.lede-project.org/project/wwan.git          | OpenWrt 3G/4G connection tool      |
+------------------------------------------------------+------------------------------------+

Getting Started
===============

1.  Install Google Repo.

    Download the Repo script and make it executable::

        $ cd ${HOME}/bin
        $ curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > repo
        $ chmod 755 repo

    Make sure the `${HOME}/bin` is in your `${PATH}` environment variable.

2.  Initialize a Repo client.

    Create an empty directory to hold your working projects::

        $ cd ${HOME}/${WORK_DIR}
        $ mkdir -p lede-projects
        $ cd lede-projects

    **NOTE**: Use whatever you want for `${WORK_DIR}` and/or `econe-yocto`, just
    adjust what follows accordingly.

    Tell Repo where to find the manifest (readonly access to github git repository)::

        $ repo init -u https://github.com/troth/lede-manifest.git

    or if you have READ/WRITE access to the manifest repository via ssh::

        $ repo init -u ssh://git@github.com/troth/lede-manifest.git

    A successful initialization will end with a message stating that Repo is
    initialized in your working directory. Your client directory should now
    contain a `.repo` directory where files such as the manifest will be kept.

3.  Fetch all the repositories.

    ::

        $repo sync

    This will result in some directoires being created and populated with git
    repositories::

        lede-manifest/
        source/
        feed/

    You should now have most of the useful git repositories for LEDE.

Staying Up to Date
==================

To pick up the latest changes for all source repositories, run::

    $ repo sync

To get back to the original detached state, run::

    $ repo sync -d
