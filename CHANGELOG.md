# Changelog

## v1.2.4

* Use Python 3.

## v1.2.3

* First release under Spinlock Labs.
* Fix Catalina support.

## v1.2.2

* Fixed handling arguments while using `ip -4` (Thanks @bsholdice)
* Fixed `ip help` (Thanks @KireinaHoro)

## v1.2.1

* Fixed error return codes and test script
* `ip neigh flush` now requires specific device (consistent behaviour with iproute2)

## v1.2.0

* Enhanced input parsing to support arbitrary length commands (Thanks @deployable)
* Simple test script added (Thanks @deployable)
* Fixed error return codes to simulate iproute2 (At this moment help messages are inconsistently printed to stderr for all errors unlinke iproute2 behaviour)

## v1.1.2

* Correctly show `src` for `ip route get` on IPv6 addresses (Thanks @codeaholics)

## v1.1.1

* Added `dev` option to `ip route add` command (Thanks @ThangCZ)

## v1.1.0

* Added source IP address to `ip route get` command
* Accepted to Homebrew master branch, tap is no longer supported

## v1.0.9

* Fixed versioning

## v1.0.8

* Better error handling and error messages (Thanks @rgcr)

## v1.0.7

* Help messages are sent to stderr (Thanks @rgcr)

## v1.0.6

* Fixed `ip -6 neigh` failing for N status flag

## v1.0.5

* Added `s` shortcuts to `show` commands (Thanks @vmoutoussamy)

## v1.0.4

* Added `ip neigh flush` (Thanks ThangCZ)
* Added 'dev' option for `ip neigh show` and `ip neigh flush`

## v1.0.3

* Fixed `ifconfig: dev: bad value` in `ip addr del`

## v1.0.2

* Interface name is concatenated to `ip addr` inet rows
