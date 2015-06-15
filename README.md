# ssl-aplus
Configurations for Qualys SSL Labs A+ ratings using various web servers

Currently supported:

- **nginx**

I welcome pull requests for additional configurations. Please provide URL
to a live server implementing the submitted config.

## Update notes (neweest first)

### June 15, 2015

Updated configs to support better DH negotiation per the Qualys recommendations,
used new recommended cipher suite the prioritizes ECDHE suites. (Export suites
were already disabled in a previous version)

Affected: nginx
