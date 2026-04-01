# Architecture

## Design goals

N5Pro is built around four principles:

* repeatability
* visibility
* safe automation
* operational recovery

## Runtime model

### On PVE

Primary tools:

* `n5pro`
* `n5pro-update`
* `n5pro-doctor`
* `n5pro-heal`
* `n5pro-backup`
* `n5pro-bootstrap-pbs`

### On PBS

Primary tools:

* `n5pro`
* `n5pro-post`
* `n5pro-doctor`

## Config

Main config file:

```text
/etc/n5pro.conf
```

This file acts as the source of truth for:

* IP addressing
* VMIDs
* MAC addresses
* storage names
* repo base URL
* datastore settings

## Update flow

1. update repo content
2. validate syntax
3. optionally reinstall local binaries
4. update local version file

## Recovery flow

1. reinstall host
2. restore repo
3. restore config
4. run `n5pro-update --install`
5. run `n5pro-doctor`
6. bootstrap PBS if needed

## Safety controls

* backups before major changes
* dry-run doctor mode
* explicit confirmation for risky actions
* lock file usage for update/bootstrap actions

