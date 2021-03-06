# Schedule

* Freeze: 2015-10-12
* Release: 2015-10-29

# 1.9.0 - Release goals

#### [#15187](https://github.com/docker/docker/issues/15187) User namespaces

User namespaces are a long awaited feature, on which [Phil Estes (@estesp)](https://github.com/estesp) did some amazing work (see [#12648](https://github.com/docker/docker/pull/12648)). Unfortunately, the integration unexpectedly conflicted with the recent introduction of [`libnetwork`](https://github.com/docker/libnetwork).

We want to fix this for 1.9.0 and be able to merge Phil's work, which means:
- All containers have their own user namespace.
- A daemon-wide setting remaps the root user for all containers.

#### [#15188](https://github.com/docker/docker/issues/15188) Better API implementation

We would like to rewrite our API, not to change the endpoint in a first phase, but at least to have a better, typed, self-documented, versioned version of the Docker API that we could share between Engine and Swarm.

#### [#14298](https://github.com/docker/docker/issues/14298) Progress towards a client-side builder

As explained in the [roadmap document](https://github.com/docker/docker/blob/master/ROADMAP.md#122-builder), we want to enable client-side build.

#### [#14212](https://github.com/docker/docker/issues/14212) Progress towards the OCI integration

The Engine currently has several compiled-in `execdriver` implementations, the default one being [`libcontainer`](https://github.com/opencontainers/runc/blob/master/libcontainer). We the apparition of the [Open Containers Initiative](https://github.com/opencontainers/specs), we want the Engine to have a single execution backend capable of shelling-out to an OCI compliant binary. Currently, the standard and default implementation of such binary is [runC](https://runc.io).

It's unlikely that this will ship as the sole, default execution backend for Docker 1.9.0, but we intend to show some progress in a separate branch.