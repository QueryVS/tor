# src/ext files

@dir /ext
@brief Externally maintained code

The "ext" directory holds code that was written elsewhere, and is not
reliably packaged as a library where we want to build, so we ship
it along with Tor.

In general, you should not edit this code: we are not the maintainers.
Instead, you should submit patches upstream.

### OpenBSD_malloc_Linux.c:

> The OpenBSD malloc implementation, ported to Linux.  Used only when
> --enable-openbsd-malloc is passed to the configure script.

### strlcat.c
### strlcpy.c

> Implementations of strlcat and strlcpy, the more sane replacements
> for strcat and strcpy.  These are nonstandard, and some libc
> implementations refuse to add them for religious reasons.

### ht.h

> An implementation of a hash table in the style of Niels Provos's
> tree.h.  Shared with Libevent.

### tinytest.c tinytest.h
### tinytest_demos.c
### tinytest_macros.h

> A unit testing framework. https://github.com/nmathewson/tinytest

### tor_queue.h

> A copy of sys/queue.h from OpenBSD.  We keep our own copy rather
> than using sys/queue.h, since some platforms don't have a
> sys/queue.h, and the ones that do have diverged in incompatible
> ways.  (CIRCLEQ or no CIRCLEQ? SIMPLQ or STAILQ?)  We also rename
> the identifiers with a TOR_ prefix to avoid conflicts with
> the system headers.

### curve25519_donna/*.c

> A copy of Adam Langley's curve25519-donna mostly-portable
> implementations of curve25519.

### csiphash.c
### siphash.h

> Marek Majkowski's implementation of siphash 2-4, a secure keyed
> hash algorithm to avoid collision-based DoS attacks against hash
> tables.

### trunnel/*.[ch]

> Headers and runtime code for Trunnel, a system for generating
> code to encode and decode binary formats.

### ed25519/ref10/*

> Daniel Bernsten's portable ref10 implementation of ed25519.
> Public domain.

### ed25519/donna/*

> Andrew Moon's semi-portable ed25519-donna implementation of
> ed25519. Public domain.

### keccak-tiny/

> David Leon Gil's portable Keccak implementation. CC0.

### readpassphrase.[ch]

> Portable readpassphrase implementation from OpenSSH portable, version
> 6.8p1.

### timeouts/

> William Ahern's hierarchical timer-wheel implementation. MIT license.

### mulodi/

> Contains an overflow-checking 64-bit signed integer multiply
> from LLVM's compiler_rt.  For some reason, this is missing from
> 32-bit libclang in many places. Dual licensed MIT-license and
> BSD-like license; see mulodi/LICENSE.TXT.
