#gh:gh_sase-org__sase We recently added (and then fixed) the `sase screenshot` command. It still
doesn't seem to work properly when used with the `--host` option (see the command output
below for context). Can you help me diagnose the root cause of this issue and fix it?
Demonstrate your fix by running the `sase screenshot --host apollo` command and then
saving the PNG image file that the command creates as a new sase artifact.

#plan %m:gpt-6-astra

```
❯ sase screenshot --host apollo
sase screenshot: sase on 'apollo' is missing or too old for `sase screenshot`; upgrade it
```