node-usage-collectd
===================

Collectd Exec Script for Internode Usage statistics

Run the included perl script using the Collectd [Exec plugin](https://collectd.org/wiki/index.php/Plugin:Exec).

Requires a data directory to specified as the only argument which will be used to locate authentication
credentials as well as be used to cache service information.

The data directory requires the presence of a ".auth" file with credentials specified:

    user:<internode user name>
    password:<password>


See the included sample .auth file for the above example.

/etc/collectd.conf:

    LoadPlugin Exec
    <Plugin exec>
        Exec "<script-user>" "/usr/bin/perl" "<install-path/node-usage-collectd/node_usage.pl <data-dir>"
    </Plugin>
