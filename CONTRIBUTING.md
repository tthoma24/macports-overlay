# Contributing

Issues and pull requests are welcome, as is reusing any of this elsewhere.

## Licensing, in plain terms

The Portfiles here are under MPL-2.0. Two things follow from that:

- If you distribute a modified Portfile from this repository, you need to make
  that file's source available under MPL-2.0 as well. The obligation is per file,
  so it does not spread to the rest of whatever you are building.
- The copyright and license notices at the top of each Portfile need to stay
  there. MPL sections 3.3 and 3.4 cover this.

What MPL-2.0 does *not* do is require you to send changes back to me. No open
source license can. So the rest of this is a request rather than a condition.

## The request

If you fix a bug, bump a version, or add a variant, please open a pull request
here. A fix that lives only in a fork is a fix nobody else finds.

## What makes a PR easy to merge

- `port lint --nitpick` is clean. You can run it from inside the port's
  directory without registering the repo or building an index:
  `cd mail/resend-cli && port lint --nitpick`
- The port installs, and `port uninstall` leaves nothing behind.
- Say which macOS version and architecture you tested on. If you touched a
  variant, say which variants you exercised.
- Checksums are `rmd160`, `sha256` and `size`. Note that GNU coreutils may
  shadow the BSD tools on a MacPorts system, so `stat -f %z` can fail where
  `wc -c` works.
- One port per commit.

## Adding a new port

Copy `Portfile.template` into `category/portname/Portfile`. The first entry in
`categories` has to match the directory the Portfile sits in, or lint warns.
