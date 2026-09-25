# Chat History - ace-run (0ar)

- **TIMESTAMP:** 2026-09-09 07:08:37 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0ar

## Prompt

#gh:gh_sase-org__sase When I run `sase machine init`, I am asked to paste an "enrollment bundle" for each machine. What is an enrollment bundle? %m:gpt-5.6-sol

## Response

I’ll trace the `machine init` command and its documentation so I can explain exactly what the bundle contains, where it comes from, and whether it is sensitive.

The key distinction is that this is not a discovery record or a general Tailscale credential. It is a short-lived, target-issued authorization artifact that lets this controller perform the initial trust handshake.

An enrollment bundle is a short-lived, single-use credential created by the target machine. It authorizes your controller to enroll with that machine’s SASE gateway and exchange the temporary secret for a durable credential.

On each target machine, run:

```bash
umask 077
sase machine bootstrap --json > /tmp/sase-bootstrap.json
```

Then, on the controller:

```bash
sase machine init -B /path/to/sase-bootstrap.json
```

The bundle contains:

- A one-time bootstrap ID and secret
- The target’s installation identity (“installation pin”)
- Supported protocol versions
- Requested authorization scopes
- An expiration time

Each machine needs its own bundle because the bundle is issued by—and pinned to—that particular SASE installation.

Treat it like a password: transfer it over a protected channel, don’t put it in command arguments or logs, and delete both temporary copies after enrollment. If it expires or gets consumed during a failed enrollment, generate a fresh one on the target.
