syslog-sign
===========

Open Source "Signed Syslog Messages" (id est: rfc5848 implementation) addon for syslog-ng.

This project aims to implement an rfc5848 compliant syslog-signer,
to be used with (initially, at least) syslog-ng (open source version).

The idea is to have something like this in the syslog-ng.conf file:

destination d_program_syslog_sign {<br/>
        program("/usr/local/sbin/syslog-sign.pl -f /usr/local/etc/syslog-sign.conf" 
                flags("syslog-protocol")
        );<br/>
};<br/>

in order to properly generate all rfc5848 records.

Signature Blocks are already implemented, Certificate Blocks 
and Signature groups still missing.
We have (optional) encryption for the output (this is outside the standard,
and suboptimal)

Some (runtime configurable) deviations from the standards are present, as the 
previous optional output encryption layer.

Giovanni Faglioni &lt; giova at faglioni dot it &gt; 

The code is under the GPLv2 or, at your option, any later version.

