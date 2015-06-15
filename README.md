# ssl-aplus
Configurations for Qualys SSL Labs A+ ratings using various web servers

Currently supported:

- **nginx**

I welcome pull requests for additional configurations. Please provide URL
to a live server implementing the submitted config.

## Implementation notes

Getting an A+ rating depends on more than configuration. You must also make sure:

1. you've got an up-to-date SSL implementation
2. you've got up-to-date web server software
3. your certificate provider has issued you a high-quality certificate (e.g. signed with good parameters, sufficient key size, has secure trust chain, etc.)

These configuration files cannot fix problems with software implementation or
key issuing/signing problems

## Update notes (neweest first)

### June 15, 2015

Updated configs to support better DH negotiation per the Qualys recommendations,
used new recommended cipher suite the prioritizes ECDHE suites. (Export suites
were already disabled in a previous version)

Affected: nginx
