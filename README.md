# macports-overlay
A MacPorts overlay that provides ports not available in upstream MacPorts. Modelled after the [macports-wine](https://github.com/Gcenx/macports-wine) repository of @Gcenx.

<br>

## This repository provides

<br>

## How to use this repository
After installing MacPorts you need a modern version of `git`\
git clone the repository into /opt then follow [4.6. Local Portfile Repositories](https://guide.macports.org/#development.local-repositories)\
Next run `port -v sync`
You can now install any of the provided Ports.

<br>

## Why these ports are not in MacPorts

The ports here either because I didn't think they would be useful to
anyone else, or because I disagree with a design decision. That may change
one day, but the important point is not that these are considered unsafe or
unfinished; anything merged to main is linted clean and tested.

resend-cli is the first. Upstream builds a self-contained binary with pkg and
distributes it that way through their own Homebrew tap and their install.sh. This
port installs that binary by default and offers a +source variant that builds from
the GitHub source archive with pnpm. MacPorts declined it on the grounds that a
source build should be the default and the variant was unnecessary. However, that
is not a written rule: the MacPorts Guide does not require source builds, and several
ports in the tree install upstream pre-built binaries without compiling anything,
including gh, kubectl, helm, terraform, 1password-cli, deno, dart-sdk, every JDK
and .NET runtime, and two other pre-built Node CLIs.

Discussion: https://github.com/macports/macports-ports/pull/33843

<br>

## Contributing

Contributions in the form of isssues/PRs and reuse are most welcome. See LICENSE.md and CONTRIBUTING.md.