#!/bin/bash
cat dns-tunneling.log | head -n 100 | tail -n 50 | awk -F '\t' 'BEGIN { print "<dnslog>" } { print "\n\""<row>""\n\t\t\<timestamp>\ " $4 "</timestamp>\,\n\t\t\<client_ip>\ \"\" $5 "</client_ip>\",\n\t\t\"<client_port>\ $6 "</client_port>\" "\n\t\<row" } END { print "<dnslog>" }' > results.xml
