Anonymize IPs from Apache logs
==============================

This reads a line from STDIN, searches for IPv4 addresses,
and replaces the last digit group with "0". It then appends
the resulting line to the filename passed as first argument to
this script.

Example
-------

This call:

    111.222.333.444 foolog

... will append this line to the file `foolog`:

    111.222.333.0

Usage in Apache config
----------------------

Make sure that `anonymize-ip` is in Apache's path or use an absolute path below:

    ErrorLog     "|anonymize-ip /opt/www/mysite/log/error.log"
    CustomLog    "|anonymize-ip /opt/www/mysite/log/access.log" combined


