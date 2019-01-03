# Package Server Protocol

## What is it?

There are several ways to install software on UNIX-like operating systems.
Even on a single Linux distribution, there are multiple package managers and
formats that all accomplish roughly the same -- installing and removing
software packages.

A *Package Server Protocol (PSP)* is an attempt to standardize the way to
manage software packages on a UNIX system.  This mostly includes adding,
updating, removing and querying packages, as well as keeping track of registers
where available packages are listed and stored.

The idea is that a *Package Server* implementing the PSP is written for each
particular package format, and these servers are then re-used by different
*Package Client* implementations (or *Package Managers*).  This way, universal
clients can be created which specialize on a particular user interface rather than a package format.

For example, an RPM server would encapsulate the RPM format (using the libdnf
API).  Then, a CLI client and a GUI-based client would both use that server to
install RPM packages as well as other servers to install Python packages and so
on.
