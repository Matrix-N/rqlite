## v8.43.1 (unreleased)
### Implementation changes and bug fixes
- [PR #2193](https://github.com/rqlite/rqlite/pull/2193): rqlite shell `.dump` supports limiting tables.

## v8.43.0 (July 31st 2025)
### New features
- [PR #2189](https://github.com/rqlite/rqlite/pull/2189): Support backing up specific tables. Fixes issue [#1381](https://github.com/rqlite/rqlite/issues/1381).

### Implementation changes and bug fixes
- [PR #2186](https://github.com/rqlite/rqlite/pull/2186): Add "running inside Kubernetes" hint to `/status`
- [PR #2190](https://github.com/rqlite/rqlite/pull/2190): Rollback transaction if restore fails. Fixes issue [#385](https://github.com/rqlite/rqlite/issues/385).
- [PR #2191](https://github.com/rqlite/rqlite/pull/2191): 'go mod' updates.

## v8.42.0 (July 25th 2025)
### New features
- [PR #2182](https://github.com/rqlite/rqlite/pull/2182): Support providing backups in DELETE mode.
- [PR #2183](https://github.com/rqlite/rqlite/pull/2183): Upgrade SQLite to 3.50.3.

### Implementation changes and bug fixes
- [PR #2180](https://github.com/rqlite/rqlite/pull/2180): Use `require` for some Go modules, instead of direct `import`.
- [PR #2184](https://github.com/rqlite/rqlite/pull/2184): Add Raft transport-level logging.

## v8.41.0 (July 23rd 2025)
### New features
- [PR #2172](https://github.com/rqlite/rqlite/pull/2172): Allow specification of target node as new Leader during Stepdown.
- [PR #2176](https://github.com/rqlite/rqlite/pull/2176): rqlite shell supports specifying ID of new leader node after stepdown.

### Implementation changes and bug fixes
- [PR #2173](https://github.com/rqlite/rqlite/pull/2173): Add `Followers()` method to Store.
- [PR #2179](https://github.com/rqlite/rqlite/pull/2179): Upgrade dependencies via 'go get'.

## v8.40.0 (July 21st 2025)
### New features
- [PR #2154](https://github.com/rqlite/rqlite/pull/2154), [PR #2156](https://github.com/rqlite/rqlite/pull/2156), [PR #2170](https://github.com/rqlite/rqlite/pull/2170): Add a HTTP API which instructs the Leader to stepdown, transferring Leadership to another node in the cluster. Fixes issue [#2153](https://github.com/rqlite/rqlite/issues/2153).
- [PR #2159](https://github.com/rqlite/rqlite/pull/2159): Add `.stepdown` command to rqlite shell.

### Implementation changes and bug fixes
- [PR #2161](https://github.com/rqlite/rqlite/pull/2161): Minor refactor of HTTP-Store interfaces.
- [PR #2149](https://github.com/rqlite/rqlite/pull/2149): Consolidate the top-level of the source tree.
- [PR #2150](https://github.com/rqlite/rqlite/pull/2150): Move various utilities into an `internal` module.
- [PR #2152](https://github.com/rqlite/rqlite/pull/2152): Remodel the main CDC loop.

## v8.39.1 (July 7th 2025)
### Implementation changes and bug fixes
- [PR #2147](https://github.com/rqlite/rqlite/pull/2147): Support timestamped uploads to Google Cloud Storage.
- [PR #2148](https://github.com/rqlite/rqlite/pull/2148): Use correct Metadata ID for GCS uploads.

## v8.39.0 (July 6th 2025)
### New features
- [PR #2144](https://github.com/rqlite/rqlite/pull/2144), [PR #2145](https://github.com/rqlite/rqlite/pull/2145), [PR #2146](https://github.com/rqlite/rqlite/pull/2146): Automatic _Backup and Restore_ now supports Google Cloud Storage.

## v8.38.3 (July 3rd 2025)
### Implementation changes and bug fixes
- [PR #2139](https://github.com/rqlite/rqlite/pull/2139): 'go mod' updates.
- [PR #2106](https://github.com/rqlite/rqlite/pull/2106), [PR #2126](https://github.com/rqlite/rqlite/pull/2126): Add initial CDC Service implementation.
- [PR #2128](https://github.com/rqlite/rqlite/pull/2128): Support CDC highwatermarking control.
- [PR #2129](https://github.com/rqlite/rqlite/pull/2129): CDC Service improvements and refactoring.
- [PR #2131](https://github.com/rqlite/rqlite/pull/2131): FIFO queue for CDC service.
- [PR #2132](https://github.com/rqlite/rqlite/pull/2132), [PR #2133](https://github.com/rqlite/rqlite/pull/2133): Move to channel-based FIFO service.
- [PR #2134](https://github.com/rqlite/rqlite/pull/2134): Leader observations are now booleans.
- [PR #2135](https://github.com/rqlite/rqlite/pull/2135): Use actual Leader Observation value.
- [PR #2137](https://github.com/rqlite/rqlite/pull/2137): Perform Disco Service reporting in a distinct goroutine.
- [PR #2138](https://github.com/rqlite/rqlite/pull/2138): Restore Disco service checking cluster service directly.

## v8.38.2 (June 23rd 2025)
### Implementation changes and bug fixes
- [PR #2119](https://github.com/rqlite/rqlite/pull/2119): CLI supports `RQLITE_HOST` as connection environment variable. Fixes issue [#2088](https://github.com/rqlite/rqlite/issues/2088). Thanks @m04f
- [PR #2124](https://github.com/rqlite/rqlite/pull/2124): Upgrade dependencies via 'go get'.

## v8.38.1 (June 19th 2025)
### Implementation changes and bug fixes
- [PR #2118](https://github.com/rqlite/rqlite/pull/2118): Query supports returning Raft Index for Strong Consistency Reads.

## v8.38.0 (June 18th 2025)
### New features
- [PR #2113](https://github.com/rqlite/rqlite/pull/2113): Support returning Raft index in responses. See [the docs](https://rqlite.io/docs/api/api/#tracking-raft-indexes) for more details.

### Implementation changes and bug fixes
- [PR #2099](https://github.com/rqlite/rqlite/pull/2099): Add basic CDC streamer to database module.
- [PR #2101](https://github.com/rqlite/rqlite/pull/2101): Add CDC support to Store component.
- [PR #2110](https://github.com/rqlite/rqlite/pull/2110): Expose Raft log index via `Store.Execute()`.
- [PR #2112](https://github.com/rqlite/rqlite/pull/2112): Expose Raft log index via `Store.Request()`.
- [PR #2114](https://github.com/rqlite/rqlite/pull/2114): Support returning Raft Index in HTTP responses.
- [PR #2115](https://github.com/rqlite/rqlite/pull/2115): Upgrade `go mod` dependencies.

## v8.37.4 (June 7th 2025)
### Implementation changes and bug fixes
- [PR #2098](https://github.com/rqlite/rqlite/pull/2098): Upgrade SQL parser.

## v8.37.3 (June 6th 2025)
### Implementation changes and bug fixes
- [PR #2097](https://github.com/rqlite/rqlite/pull/2097): Upgrade SQL parser.

## v8.37.2 (May 30th 2025)
### Implementation changes and bug fixes
- [PR #2092](https://github.com/rqlite/rqlite/pull/2092): Update Go module dependencies, Go version to 1.23.8, and toolchain to go1.23.9.
- [PR #2095](https://github.com/rqlite/rqlite/pull/2095): Upgrade SQL parser.

## v8.37.1 (May 27th 2025)
### Implementation changes and bug fixes
- [PR #2090](https://github.com/rqlite/rqlite/pull/2090): Prevent a single-node cluster from joining another cluster. Fixes issue [#2087](https://github.com/rqlite/rqlite/issues/2087).

## v8.37.0 (May 1st 2025)
This release adds support for automatically reloading all X.509 certificates and keys. rqlite does this by monitoring the relevant files, reloading the information as needed. Previous releases required that rqlite be restarted to pick up new X.509 resources.
### New features
- [PR #2080](https://github.com/rqlite/rqlite/pull/2080), [PR #2081](https://github.com/rqlite/rqlite/pull/2081), [PR #2082](https://github.com/rqlite/rqlite/pull/2082), [PR #2084](https://github.com/rqlite/rqlite/pull/2084): Support x.509 cert reloading via simpler lazy load.
- [PR #2069](https://github.com/rqlite/rqlite/pull/2069): Add TLS certificate monitoring and automatic reload to HTTP server.
- [PR #2071](https://github.com/rqlite/rqlite/pull/2071): Add server TLS certificate monitoring and automatic reload to inter-node communications.
- [PR #2076](https://github.com/rqlite/rqlite/pull/2076): Add client TLS certificate monitoring and automatic reload to inter-node communications.

### Implementation changes and bug fixes
- [PR #2064](https://github.com/rqlite/rqlite/pull/2064), [PR #2068](https://github.com/rqlite/rqlite/pull/2068), [PR #2072](https://github.com/rqlite/rqlite/pull/2072), [PR #2073](https://github.com/rqlite/rqlite/pull/2073): Add polling-based certificate file monitor.
- [PR #2070](https://github.com/rqlite/rqlite/pull/2070): Add a `Close` method to the `tcp.Mux` type.
- [PR #2074](https://github.com/rqlite/rqlite/pull/2074): Support setting TLS client config GetCertificate function.
- [PR #2077](https://github.com/rqlite/rqlite/pull/2077): Replace `interface{}` with `any`.

## v8.36.18 (April 19th 2025)
There are no functional changes to rqlite in this release. The only changes are fixes for Docker image creation.
### Implementation changes and bug fixes
- [96f603d](https://github.com/rqlite/rqlite/commit/96f603d74c4d0f94949fbc596244606baaf557d9): Enable `curl` redirects when building _sqlite-vec_ to address [Docker build failures](https://github.com/rqlite/rqlite/actions/runs/14545179069).

## v8.36.17 (April 18th 2025)
### Implementation changes and bug fixes
- [PR #2061](https://github.com/rqlite/rqlite/pull/2061): Support registering Update Hooks at the database level.
- [PR #2062](https://github.com/rqlite/rqlite/pull/2062): Support registering Commit Hooks at the database level.
- [PR #2066](https://github.com/rqlite/rqlite/pull/2066): Update dependencies.
- [PR #2067](https://github.com/rqlite/rqlite/pull/2067): Update SQLite to 3.49.1.

## v8.36.16 (April 3rd 2025)
There are no functional changes to rqlite in this release. The only changes are improvements to the Docker image.
### Implementation changes and bug fixes
- [64f7ef7](https://github.com/rqlite/rqlite/commit/64f7ef7f738c9973770c3620a65692b538a49a3a): Docker image supports enabling Foreign Key constraints via an Environment variable.

## v8.36.15 (March 31st 2025)
### Implementation changes and bug fixes
- [PR #2057](https://github.com/rqlite/rqlite/pull/2057): Minor refactoring of HTTP Leader checks.
- [PR #2058](https://github.com/rqlite/rqlite/pull/2058): Add transaction status for each connection to DB stats.
- [PR #2059](https://github.com/rqlite/rqlite/pull/2059): Upgrade dependencies.

## v8.36.14 (March 15th 2025)
### Implementation changes and bug fixes
- [PR #2056](https://github.com/rqlite/rqlite/pull/2056): Minor refactoring of HTTP credentials handling.
- [PR #2054](https://github.com/rqlite/rqlite/pull/2054): Bump golang.org/x/net from 0.35.0 to 0.36.0.
- [PR #2055](https://github.com/rqlite/rqlite/pull/2055): Support SQL-format loading via Follower. Fixes issue [#2053](https://github.com/rqlite/rqlite/issues/2053).

## v8.36.13 (March 11th 2025)
### Implementation changes and bug fixes
- [PR #2051](https://github.com/rqlite/rqlite/pull/2051): System-level test of SQL format backups.
- [PR #2052](https://github.com/rqlite/rqlite/pull/2052): Compress SQL-format backups during transmission. Fixes issue [#2050](https://github.com/rqlite/rqlite/issues/2050).

## v8.36.12 (February 28th 2025)
### Implementation changes and bug fixes
- [PR #2044](https://github.com/rqlite/rqlite/pull/2044): Simplify random package with math/rand/v2. Thanks @alexandear.
- [PR #2048](https://github.com/rqlite/rqlite/pull/2048): Upgrade `go mod` dependencies.
 
## v8.36.11 (February 4th 2025)
### Implementation changes and bug fixes
- [PR #2039](https://github.com/rqlite/rqlite/pull/2039): Some small fixes.
- [PR #2043](https://github.com/rqlite/rqlite/pull/2043): Upgrade dependencies, including DNS disco client code.

## v8.36.10 (January 27th 2025)
### Implementation changes and bug fixes
- [PR #2038](https://github.com/rqlite/rqlite/pull/2038): Further consistent use of HTTP client in rqlite shell.

## v8.36.9 (January 27th 2025)
### Implementation changes and bug fixes
- [PR #2036](https://github.com/rqlite/rqlite/pull/2036): Use configured HTTP client consistently in rqlite shell.

## v8.36.8 (January 23rd 2025)
There are no changes in this release relative to v8.36.7, but the release process now [pins](https://github.com/rqlite/rqlite/commit/2e68c6e5a196d890ccb35f5138d34aa983f66418) the version of operating system which builds the release. [`gcc` is crashing during compilation](https://github.com/rqlite/rqlite/actions/runs/12931997973/job/36074588013#step:7:836) on the latest Ubuntu image.

## v8.36.7 (January 23rd 2025)
### Implementation changes and bug fixes
- [PR #2029](https://github.com/rqlite/rqlite/pull/2029): Add basic preupdate hook support at database level.
- [PR #2030](https://github.com/rqlite/rqlite/pull/2030), [PR #2031](https://github.com/rqlite/rqlite/pull/2031): Improve preupdate hook stats and error handling.
- [PR #2032](https://github.com/rqlite/rqlite/pull/2032): Support preupdate hook for row ID values only.
- [PR #2033](https://github.com/rqlite/rqlite/pull/2033): Preupdate hook complex data testing.
- [PR #2034](https://github.com/rqlite/rqlite/pull/2034): Fix CLI panic when no hosts are available.

## v8.36.6 (January 19th 2025)
### Implementation changes and bug fixes
- [PR #2022](https://github.com/rqlite/rqlite/pull/2022): Simplify some testing by using `t.TempDir()`. Thanks @alexandear.
- [PR #2021](https://github.com/rqlite/rqlite/pull/2021): Fix typos in Help strings. Thanks @alexandear.
- [PR #2024](https://github.com/rqlite/rqlite/pull/2024): Improve variable name in SQL parsing code.
- [PR #2025](https://github.com/rqlite/rqlite/pull/2025): Optimize need-to-parse logic.
- [PR #2026](https://github.com/rqlite/rqlite/pull/2026): Recover from any panic in SQL parser.

## v8.36.5 (January 11th 2025)
### Implementation changes and bug fixes
- [PR #2018](https://github.com/rqlite/rqlite/pull/2018): Upgrade `go mod` dependencies.
- [PR #2017](https://github.com/rqlite/rqlite/pull/2017): Upgrade to rqlite/go-sqlite3 v1.37.0.

## v8.36.4 (January 9th 2025)
This change fixes an issue whereby SQLite extensions were not loaded under certain restore-from-backup scenarios. All users of SQLite extensions should upgrade to this release.
### Implementation changes and bug fixes
- [PR #2012](https://github.com/rqlite/rqlite/pull/2012), [PR #2013](https://github.com/rqlite/rqlite/pull/2013), [PR #2014](https://github.com/rqlite/rqlite/pull/2014), [PR #2015](https://github.com/rqlite/rqlite/pull/2015), [PR #2016](https://github.com/rqlite/rqlite/pull/2016): Reload SQLite extensions after swapping in a new database. Fixes issue [#2011](https://github.com/rqlite/rqlite/issues/2011).

## v8.36.3 (December 27th 2024)
### Implementation changes and bug fixes
- [PR #2000](https://github.com/rqlite/rqlite/pull/2000): Reduce memory allocations in `queryStmtWithConn`. Thanks @arturmelanchyk
- [PR #2002](https://github.com/rqlite/rqlite/pull/2002): Rename `COMMAND_TYPE_GET_NODE_API_URL` to `COMMAND_TYPE_GET_NODE_META`.
- [PR #2003](https://github.com/rqlite/rqlite/pull/2003): Pass around `NodeMeta` objects instead of strings.
- [PR #2004](https://github.com/rqlite/rqlite/pull/2004): Hook up node version within `NodeMeta`.
- [PR #2005](https://github.com/rqlite/rqlite/pull/2005): Rename `GetAddresser` interface.
- [PR #2006](https://github.com/rqlite/rqlite/pull/2006): Add version information to `/nodes` output. Fixes issue [#2001](https://github.com/rqlite/rqlite/issues/2001).

## v8.36.2 (December 24th 2024)
### Implementation changes and bug fixes
- [PR #1999](https://github.com/rqlite/rqlite/pull/1999): `go mod` updates.
- [PR #1995](https://github.com/rqlite/rqlite/pull/1995), [PR #1997](https://github.com/rqlite/rqlite/pull/1997), [PR #1998](https://github.com/rqlite/rqlite/pull/1998): Use [flagforge](https://github.com/rqlite/flagforge) to generate command-line flags.

## v8.36.1 (December 17th 2024)
### Implementation changes and bug fixes
- [PR #1994](https://github.com/rqlite/rqlite/pull/1994): Bump golang.org/x/crypto from 0.30.0 to 0.31.0.

## v8.36.0 (December 12th 2024)
### New features
- [PR #1992](https://github.com/rqlite/rqlite/pull/1992): Support executes as raw POST bodies.

### Implementation changes and bug fixes
- [PR #1993](https://github.com/rqlite/rqlite/pull/1993): `go mod` updates.

## v8.35.0 (December 11th 2024)
### New features
- [PR #1991](https://github.com/rqlite/rqlite/pull/1991): Support queries as raw POST bodies.

### Implementation changes and bug fixes
- [PR #1988](https://github.com/rqlite/rqlite/pull/1988): Automatically generate flags and associated documentation.
- [PR #1989](https://github.com/rqlite/rqlite/pull/1989): Rename flags package to rflags.
- [PR #1988](https://github.com/rqlite/rqlite/pull/1988): Upgrade dependencies.

## v8.34.3 (November 27th 2024)
### Implementation changes and bug fixes
- [PR #1986](https://github.com/rqlite/rqlite/pull/1986): Improve logging a little bit, making operation clearer and easier.

## v8.34.2 (November 25th 2024)
### Implementation changes and bug fixes
- [PR #1981](https://github.com/rqlite/rqlite/pull/1981): Upgrade dependencies.
- [PR #1982](https://github.com/rqlite/rqlite/pull/1982): Minor DB-layer improvements.

## v8.34.1 (November 14th 2024)
### Implementation changes and bug fixes
- [PR #1979](https://github.com/rqlite/rqlite/pull/1979): Preserve backward compatibility for S3 backup endpoint.

## v8.34.0 (November 11th 2024)
### New features
- [PR #1977](https://github.com/rqlite/rqlite/pull/1977): Support `randomblob(N)` by rewriting the statement.

## v8.33.0 (November 7th 2024)
### New features
- [PR #1976](https://github.com/rqlite/rqlite/pull/1976): Rewrite time and date functions so they are deterministic. Fixes issue [#536](https://github.com/rqlite/rqlite/issues/536).

### Implementation changes and bug fixes
- [PR #1975](https://github.com/rqlite/rqlite/pull/1975): Upgrade to latest SQL parser.

## v8.32.7 (November 5th 2024)
### Implementation changes and bug fixes
- [PR #1973](https://github.com/rqlite/rqlite/pull/1973): Include any failure message in `/status` output.
- [PR #1974](https://github.com/rqlite/rqlite/pull/1974): Upgrade dependencies including the SQL parser.

## v8.32.6 (November 4th 2024)
### Implementation changes and bug fixes
- [PR #1965](https://github.com/rqlite/rqlite/pull/1965): Prep S3-related testing with Minio.
- [PR #1966](https://github.com/rqlite/rqlite/pull/1966): Explicitly close Raft network streams on shutdown.
- [PR #1967](https://github.com/rqlite/rqlite/pull/1967): End-to-end testing with Minio.
- [PR #1969](https://github.com/rqlite/rqlite/pull/1969): Simpler AWS client String() implementation. Fixes issue [#1968](https://github.com/rqlite/rqlite/issues/1968).
- [PR #1972](https://github.com/rqlite/rqlite/pull/1972): Skip and log stats that return error. Fixes issue [#1971](https://github.com/rqlite/rqlite/issues/1971).

## v8.32.5 (October 31st 2024)
### Implementation changes and bug fixes
- [PR #1958](https://github.com/rqlite/rqlite/pull/1958): Improve testing of concurrent Linearizable reads.
- [PR #1959](https://github.com/rqlite/rqlite/pull/1959): Return error specific to FSM timeouts.
- [PR #1962](https://github.com/rqlite/rqlite/pull/1962): End-to-end auto-backup and auto-restore test.
- [PR #1963](https://github.com/rqlite/rqlite/pull/1963): Upgrade dependencies.
- [PR #1964](https://github.com/rqlite/rqlite/pull/1964): Return HTTP 204 if there is nothing to snapshot.

## v8.32.4 (October 23rd 2024)
### Implementation changes and bug fixes
- [PR #1957](https://github.com/rqlite/rqlite/pull/1957): Convert Linearizable Read to Strong Read if necessary.
- [PR #1955](https://github.com/rqlite/rqlite/pull/1955), [PR #1956](https://github.com/rqlite/rqlite/pull/1956): Keep track of Term of most recent Strong Read.

## v8.32.3 (October 17th 2024)
### Implementation changes and bug fixes
- [PR #1947](https://github.com/rqlite/rqlite/pull/1947): Add atomic monotonic Uint64 to rsync module.
- [PR #1949](https://github.com/rqlite/rqlite/pull/1949): Store uses timeout for linearizable read.
- [PR #1950](https://github.com/rqlite/rqlite/pull/1950): Linearizable reads VerifyLeader must happen in same term.

## v8.32.2 (October 15th 2024)
This release corrects the implementation of Linearizable reads so they implement exactly the process described in section 6.4 of the [Raft dissertation](https://raw.githubusercontent.com/ongardie/dissertation/refs/heads/master/online.pdf) by Diego Ongaro.
### Implementation changes and bug fixes
- [PR #1944](https://github.com/rqlite/rqlite/pull/1944): Correct implementation of linearizable reads.
- [PR #1945](https://github.com/rqlite/rqlite/pull/1945): Convert DB timeout to nanoseconds correctly.
- [PR #1946](https://github.com/rqlite/rqlite/pull/1946): Support configurable Linearizable read timeouts.

## v8.32.1 (October 13th 2024)
### Implementation changes and bug fixes
- [PR #1943](https://github.com/rqlite/rqlite/pull/1943): rqlite shell supports enabling Linearizable reads.

## v8.32.0 (October 13th 2024)
### New features
- [PR #1930](https://github.com/rqlite/rqlite/pull/1930), [PR #1935](https://github.com/rqlite/rqlite/pull/1935), [PR #1936](https://github.com/rqlite/rqlite/pull/1936), [PR #1937](https://github.com/rqlite/rqlite/pull/1937), [PR #1938](https://github.com/rqlite/rqlite/pull/1938): Add Linearizable reads. Thanks @lalalalatt, @peterxcli

### Implementation changes and bug fixes
- [PR #1933](https://github.com/rqlite/rqlite/pull/1933), [PR #1934](https://github.com/rqlite/rqlite/pull/1934): Add `CloseOrTimeout` utility to rsync module.
- [PR #1940](https://github.com/rqlite/rqlite/pull/1940): Tighten up IsServing HTTP checker.
- [PR #1941](https://github.com/rqlite/rqlite/pull/1941): Validate Raft log at start-up.
- [PR #1942](https://github.com/rqlite/rqlite/pull/1942): Refactor IsServing HTTP checker.

## v8.31.3 (October 7th 2024)
### Implementation changes and bug fixes
- [PR #1923](https://github.com/rqlite/rqlite/pull/1923): Node can retrieve commit index of other node.
- [PR #1924](https://github.com/rqlite/rqlite/pull/1924): Add ReadyTarget synchronization primitive.
- [PR #1925](https://github.com/rqlite/rqlite/pull/1925), [6695c7d](https://github.com/rqlite/rqlite/commit/6695c7d91fd0468fc21799e5657d58a517fce11b): Use ReadyTarget primitive to avoid timer-based polling.
- [PR #1926](https://github.com/rqlite/rqlite/pull/1926): Support reset of ReadyTargets.
- [PR #1927](https://github.com/rqlite/rqlite/pull/1927): Unit test reset of ReadyTargets.
- [PR #1928](https://github.com/rqlite/rqlite/pull/1928): Use new PollTrue primitive in Store.
- [PR #1931](https://github.com/rqlite/rqlite/pull/1931): `go mod` updates.
- [PR #1932](https://github.com/rqlite/rqlite/pull/1932): Trivial refactor of Auto read consistency logic.

## v8.31.2 (September 28th 2024)
### Implementation changes and bug fixes
- [PR #1915](https://github.com/rqlite/rqlite/pull/1915): Move VACUUM-related testing to its own files.
- [PR #1916](https://github.com/rqlite/rqlite/pull/1916): Add a "full cycle" compacting WAL scanner unit test.
- [PR #1917](https://github.com/rqlite/rqlite/pull/1917): Update "DB last modified time" on Restore.
- [PR #1918](https://github.com/rqlite/rqlite/pull/1918): Store snapshotted WAL data in a file, not in memory.
- [PR #1920](https://github.com/rqlite/rqlite/pull/1920): _AutoVac_ should just `VACUUM`, not `VACUUM INTO`. Fixes issue [#1914](https://github.com/rqlite/rqlite/issues/1914).
- [PR #1921](https://github.com/rqlite/rqlite/pull/1921): Remove unneeded Query Transaction mutex.

## v8.31.1 (September 27th 2024)
### Implementation changes and bug fixes
- [PR #1911](https://github.com/rqlite/rqlite/pull/1911): Factor out `ReadyChans` so it can be more widely used.
- [PR #1912](https://github.com/rqlite/rqlite/pull/1912): Simplify Store _Ready_ check.
- [PR #1913](https://github.com/rqlite/rqlite/pull/1913), [3063925](https://github.com/rqlite/rqlite/commit/30639258e122b24194b10058bf56dae53d428d03): Trigger full snapshot if database file is modified externally. Fixes issue [#1613](https://github.com/rqlite/rqlite/issues/1613).

## v8.31.0 (September 24th 2024)
### New features
- [PR #1910](https://github.com/rqlite/rqlite/pull/1910): Support for byte arays and hex-encoded values as Parameterized values.

### Implementation changes and bug fixes
- [PR #1906](https://github.com/rqlite/rqlite/pull/1906): Exit if _Full Needed_ flag cannot be set.
- [PR #1906](https://github.com/rqlite/rqlite/pull/1906): Count Snapshot-Persist operations.
- [PR #1908](https://github.com/rqlite/rqlite/pull/1908): Allow read-locks to be upgraded to write locks.

## v8.30.5 (September 23rd 2024)
This release addresses [a highly unlikely failure case](https://github.com/rqlite/rqlite/pull/1905) which may result in data loss. This issue has never been reported in production, **but all users of the 8.x series should upgrade to this release** to eliminate any risk of hitting the issue.
### Implementation changes and bug fixes
- [PR #1903](https://github.com/rqlite/rqlite/pull/1903): Don't take unnecessary snapshots before backups.
- [PR #1905](https://github.com/rqlite/rqlite/pull/1905): If persisting a Snapshot fails, then a _full_ snapshot is needed next snapshot cycle.

## v8.30.4 (September 20th 2024)
### Implementation changes and bug fixes
- [PR #1894](https://github.com/rqlite/rqlite/pull/1894): More use of common gzip utils.
- [PR #1896](https://github.com/rqlite/rqlite/pull/1896): Reset Store state on open.
- [PR #1897](https://github.com/rqlite/rqlite/pull/1897): Deflake DBAppliedIdx unit tests.
- [PR #1899](https://github.com/rqlite/rqlite/pull/1899): Synchronize closing a Store and performing a Snapshot.
- [PR #1900](https://github.com/rqlite/rqlite/pull/1900): Add a finalizer to the FSM Snapshot in the Store.
- [PR #1901](https://github.com/rqlite/rqlite/pull/1901): Deflake Store Provider unit tests.

## v8.30.3 (September 16th 2024)
### Implementation changes and bug fixes
- [PR #1889](https://github.com/rqlite/rqlite/pull/1889): Miscellaneous improvements to testing.
- [PR #1890](https://github.com/rqlite/rqlite/pull/1890): Rename and tweak internal Store-level function.
- [PR #1891](https://github.com/rqlite/rqlite/pull/1891): Minor improvements to code.
- [PR #1892](https://github.com/rqlite/rqlite/pull/1892): Don't ignore any error from `BootstrapCluster`.
- [PR #1893](https://github.com/rqlite/rqlite/pull/1893): `go mod` updates.

## v8.30.2 (September 10th 2024)
### Implementation changes and bug fixes
- [PR #1884](https://github.com/rqlite/rqlite/pull/1884): Refactor code to further use common utilities.
- [PR #1887](https://github.com/rqlite/rqlite/pull/1887): Improve stats and error message for Queued Wait timeouts.
- [PR #1888](https://github.com/rqlite/rqlite/pull/1888): Count cluster client read and write timeouts

## v8.30.1 (September 9th 2024)
### Implementation changes and bug fixes
- [PR #1877](https://github.com/rqlite/rqlite/pull/1877): Move to no-checkpoint-on-database-close.
- [PR #1880](https://github.com/rqlite/rqlite/pull/1880): Improve DB mode checks.
- [PR #1881](https://github.com/rqlite/rqlite/pull/1881): Add GZIP-related utils.
- [PR #1882](https://github.com/rqlite/rqlite/pull/1882): Force creation of WAL-related files when the database is opened.
- [PR #1883](https://github.com/rqlite/rqlite/pull/1883): Upgrade to rqlite SQLite v1.36.0, bringing in [Geopoly](https://www.sqlite.org/geopoly.html) support.

## v8.30.0 (September 5th 2024)
### New features
- [PR #1879](https://github.com/rqlite/rqlite/pull/1879): Add support for automatic [`PRAGMA optimize`](https://www.sqlite.org/pragma.html#pragma_optimize) of the SQLite database. Fixes issue [#1831](https://github.com/rqlite/rqlite/issues/1831).

## v8.29.5 (September 4th 2024)
### Implementation changes and bug fixes
- [PR #1878](https://github.com/rqlite/rqlite/pull/1878): Upgrade SQLite to 3.46.1.
- [PR #1875](https://github.com/rqlite/rqlite/pull/1875): Add `UPSERT` unit test.

## v8.29.4 (August 31st 2024)
### Implementation changes and bug fixes
- Correct parallel multi-platform Docker release process.

## v8.29.3 (August 31st 2024)
### Implementation changes and bug fixes
- [PR #1872](https://github.com/rqlite/rqlite/pull/1872): Upgrade Hashicorp Raft to v1.7.1.
- [PR #1873](https://github.com/rqlite/rqlite/pull/1873): Upgrade to AWS SDK v2. Fixes issue [#1655](https://github.com/rqlite/rqlite/issues/1655).

## v8.29.2 (August 26th 2024)
There are no functional changes to rqlite in this release, but it does improve the rqlite Docker images.
### Implementation changes and bug fixes
- Store SQLite extensions as Zip archives in rqlite Docker image.
- Simplify Docker build and scripts.

## v8.29.1 (August 23rd 2024)
### Implementation changes and bug fixes
- [PR #1869](https://github.com/rqlite/rqlite/pull/1869): Remove `vfsstat.c` from _misc_ extensions as it's causing a panic.
- [PR #1870](https://github.com/rqlite/rqlite/pull/1870): End-to-end node test with misc. extensions loaded.

## v8.29.0 (August 23rd 2024)
This release adds more extensions to the Docker image, as well as improving management of those extensions.
### New features
- [PR #1859](https://github.com/rqlite/rqlite/pull/1859), [PR #1860](https://github.com/rqlite/rqlite/pull/1864), [PR #1860](https://github.com/rqlite/rqlite/pull/1864): `-extensions-path` supports multiple comma-delimited paths.
- [PR #1868](https://github.com/rqlite/rqlite/pull/1868): Support `CUSTOM_SQLITE_EXTENSIONS_PATH` in Docker image.

### Implementation changes and bug fixes
- [PR #1863](https://github.com/rqlite/rqlite/pull/1863), [PR #1865](https://github.com/rqlite/rqlite/pull/1865), [PR #1867](https://github.com/rqlite/rqlite/pull/1867): Add miscellaneous extensions from SQLite source to Docker image.
- [PR #1861](https://github.com/rqlite/rqlite/pull/1861): Remove differences between CircleCI and release build `go install` flags.
- [PR #1862](https://github.com/rqlite/rqlite/pull/1862): `go mod` updates.
- [7f36802](https://github.com/rqlite/rqlite/commit/7f368026afcfac4ae09a505206de9c1759d7dbaa): Docker image actually only needs the single-file SQLean bundle.

## v8.28.4 (August 16th 2024)
There are no functional changes in this release to rqlite itself.
### Implementation changes and bug fixes
- Add the [SQLite ICU extension](https://sqlite.org/src/dir/ext/icu) to the Docker image.

## v8.28.3 (August 15th 2024)
### Implementation changes and bug fixes
- [PR #1857](https://github.com/rqlite/rqlite/pull/1857): rqlite shell supports listing loaded SQLite extensions.

## v8.28.2 (August 14th 2024)
This release adds the [Sqlean](https://github.com/nalgeon/sqlean) and [sqlite-vec](https://github.com/asg017/sqlite-vec/tree/main) SQLite extensions to the Docker image, allowing them to be loaded at launch-time.
### Implementation changes and bug fixes
- [PR #1856](https://github.com/rqlite/rqlite/pull/1856): Add Sqlean and sqlite-vec to the Docker image.

## v8.28.1 (August 13th 2024)
This release builds the Docker image so that it can load SQLite extensions. It also places precompiled [SQLean extensions](https://github.com/nalgeon/sqlean) in `/opt/extensions` ready for loading.
### Implementation changes and bug fixes
- [PR #1854](https://github.com/rqlite/rqlite/pull/1854): More test coverage of SQLite Extensions support.
- [PR #1855](https://github.com/rqlite/rqlite/pull/1855): Generate protobuf code using latest protoc

## v8.28.0 (August 10th 2024)
### New features
- [PR #1853](https://github.com/rqlite/rqlite/pull/1853): Support loading a single SQLite extension from a file.

## v8.27.0 (August 9th 2024)
This release adds support for loading SQLite extensions when rqlite launches. Check out [the docs](https://rqlite.io/docs/guides/extensions/) for full details.
### New features
- [PR #1844](https://github.com/rqlite/rqlite/pull/1844), [PR #1848](https://github.com/rqlite/rqlite/pull/1848), [PR #1849](https://github.com/rqlite/rqlite/pull/1849): Support loading SQLite extensions at launch time.
- [PR #1852](https://github.com/rqlite/rqlite/pull/1852): Support loading SQLite extensions as Gzipped tarballs.

### Implementation changes and bug fixes
- [PR #1845](https://github.com/rqlite/rqlite/pull/1845): Don't disable SQLite extension loading in the build.

## v8.26.9 (August 7th 2024)
### Implementation changes and bug fixes
- [PR #1842](https://github.com/rqlite/rqlite/pull/1842): Move to "named" registration of the SQLite3 driver.
- [PR #1843](https://github.com/rqlite/rqlite/pull/1843): `go mod` updates.

## v8.26.8 (July 28th 2024)
This release blocks execution of `PRAGMA` statements which will break rqlite.
### Implementation changes and bug fixes
- [PR #1836](https://github.com/rqlite/rqlite/pull/1836): Don't perform a consistency check of empty Snapshot stores.
- [PR #1838](https://github.com/rqlite/rqlite/pull/1838): Prevent execution of PRAGMAs which will break rqlite.

## v8.26.7 (July 12th 2024)
### Implementation changes and bug fixes
- [PR #1834](https://github.com/rqlite/rqlite/pull/1834): Fix timestamped uploads so they actually use current timestamp. Fixes issue [#1833](https://github.com/rqlite/rqlite/issues/1833). Thanks @alexgreendesign

## v8.26.6 (July 4th 2024)
### Implementation changes and bug fixes
- [PR #1830](https://github.com/rqlite/rqlite/pull/1830): Support upgrading 7.x snapshots that contain no data.

## v8.26.5 (July 4th 2024)
There are no changes in this release relative to v8.26.4, but now the [Linux release binaries dynamically link](https://github.com/rqlite/rqlite/commit/2c56d16791e2729673c36dce19e1de3de6df572e) [glibc](https://www.gnu.org/software/libc/).

## v8.26.4 (July 3rd 2024)
### Implementation changes and bug fixes
- [PR #1826](https://github.com/rqlite/rqlite/pull/1826): Simplify CAS implementation.
- [PR #1827](https://github.com/rqlite/rqlite/pull/1826): Add more 7.x-to-8.x upgrade logging.
- [PR #1828](https://github.com/rqlite/rqlite/pull/1828): Perform more cleanup if upgrade from 7.x fails.

## v8.26.3 (July 1st 2024)
### Implementation changes and bug fixes
- [PR #1814](https://github.com/rqlite/rqlite/pull/1814): Use enum for SQLite synchronous mode.
- [PR #1815](https://github.com/rqlite/rqlite/pull/1815): Track latest Raft Term in FSM.
- [PR #1816](https://github.com/rqlite/rqlite/pull/1816): Support `SetSynchronousMode` on `SwappableDB`.
- [PR #1824](https://github.com/rqlite/rqlite/pull/1824): More CAS logging.
- [PR #1825](https://github.com/rqlite/rqlite/pull/1825): `go mod` updates.

## v8.26.2 (June 20th 2024)
### Implementation changes and bug fixes
- [PR #1809](https://github.com/rqlite/rqlite/pull/1809): rqlite shell supports triggering Raft snapshots.
- [PR #1811](https://github.com/rqlite/rqlite/pull/1811): Log failed user-requested snapshots.

## v8.26.1 (June 19th 2024)
### Implementation changes and bug fixes
- [PR #1808](https://github.com/rqlite/rqlite/pull/1808): Associate "owners" with Check-and-Sets. See issue [#1807](https://github.com/rqlite/rqlite/issues/1807).

## v8.26.0 (June 14th 2024)
This release sees the addition of a new API, which allows users to trigger a Raft snapshot and Log Truncation (see the [Raft paper](https://raft.github.io/raft.pdf) for an explanation). This is mostly useful for test purposes, but may have operational value occassionally.

### New features
- [PR #1804](https://github.com/rqlite/rqlite/pull/1804): Raft snapshots can now be triggered via a HTTP API request.

### Implementation changes and bug fixes
- [PR #1800](https://github.com/rqlite/rqlite/pull/1800): Close network resources before closing the Store.
- [PR #1801](https://github.com/rqlite/rqlite/pull/1801): Upgrade to rqlite/go-sqlite3 v1.33.0.

## v8.25.1 (June 10th 2024)
### Implementation changes and bug fixes
- [PR #1797](https://github.com/rqlite/rqlite/pull/1797): Upgrade Hashicorp Raft to v1.7.0.

## v8.25.0 (June 8th 2024)
### New features
- [PR #1796](https://github.com/rqlite/rqlite/pull/1796): Add new read-consistency level "auto".

## v8.24.11 (June 5th 2024)
### Implementation changes and bug fixes
- [PR #1790](https://github.com/rqlite/rqlite/pull/1790): Register Mux Stats.
- [PR #1792](https://github.com/rqlite/rqlite/pull/1792): Check some unchecked errors, fixing a small bug in the process.

## v8.24.10 (June 1st 2024)
### Implementation changes and bug fixes
- [PR #1789](https://github.com/rqlite/rqlite/pull/1789): `go mod` updates.

## v8.24.9 (May 31st 2024)
This is the first release for which there are [multi-platform Docker images](https://hub.docker.com/r/rqlite/rqlite) available.
### Implementation changes and bug fixes
- [PR #1788](https://github.com/rqlite/rqlite/pull/1788): Add support for Trace profiling.

## v8.24.8 (May 28th 2024)
This releases improves memory usage during HTTP request processing by decoding any JSON requests bodies using streaming reads, as opposed to reading the entire request into memory first.
### Implementation changes and bug fixes
- [PR #1783](https://github.com/rqlite/rqlite/pull/1783): Minor improvements to Queue handling.
- [PR #1786](https://github.com/rqlite/rqlite/pull/1786): Streaming JSON decoding during request parsing.
- [PR #1787](https://github.com/rqlite/rqlite/pull/1787): HTTP Request Parser now takes a Reader, not a byte slice.

## v8.24.7 (May 10th 2024)
Build release assets on [ubuntu-20.04](https://github.com/rqlite/rqlite/commit/0c7fd1c8cb7deae4055102233ff3e9c0bb3369fd).

## v8.24.6 (May 10th 2024)
Reinstates static linking for amd64 builds on Linux during the official release process.

### Implementation changes and bug fixes
- [PR #1779](https://github.com/rqlite/rqlite/pull/1779): Log more information about compilation.

## v8.24.5 (May 10th 2024)
There are no changes in this release relative to v8.24.2. However this release remove static linking for all architecture types, since it can be problematic in the long run.

## v8.24.4 (May 10th 2024)
### Implementation changes and bug fixes
- [PR #1778](https://github.com/rqlite/rqlite/pull/1778): `go mod` updates.

## v8.24.3 (May 10th 2024)
There are no changes in this release relative to v8.24.2. This release simply moves rqlite to a GitHub-actions build-and-release process.

## v8.24.2 (May 4th 2024)
### Implementation changes and bug fixes
- [PR #1776](https://github.com/rqlite/rqlite/pull/1776): Allow multiple Snapshots to be read concurrently from the Snapshot Store.
- [PR #1777](https://github.com/rqlite/rqlite/pull/1777): `go mod` updates.

## v8.24.1 (May 3rd 2024)
### Implementation changes and bug fixes
- [PR #1775](https://github.com/rqlite/rqlite/pull/1775): Synchronize opening Snapshot Store and Snapshotting. Fixes issue [#1774](https://github.com/rqlite/rqlite/issues/1774).

## v8.24.0 (May 3rd 2024)
This release supports optionally adding a timestamp to the name of any auto-uploaded backup. This allows you to automatically upload point-in-time backups.
### New features
- [PR #1773](https://github.com/rqlite/rqlite/pull/1773): Support timestamp auto-uploaded backups. Fixes issue [#1771](https://github.com/rqlite/rqlite/issues/1771).

### Implementation changes and bug fixes
- [PR #1765](https://github.com/rqlite/rqlite/pull/1765): Synchronize accesses to HTTP Server's AllowOrigin value. Fixes issue [#1764](https://github.com/rqlite/rqlite/issues/1764).
- [PR #1768](https://github.com/rqlite/rqlite/pull/1768): Improve backup-related instrumentation.
- [PR #1769](https://github.com/rqlite/rqlite/pull/1769): Run end-to-end testing with INFO-level logging.
- [PR #1772](https://github.com/rqlite/rqlite/pull/1772): Remove unused `compress` flag in auto-upload code.

## v8.23.4 (April 26th 2024)
### Implementation changes and bug fixes
- [PR #1760](https://github.com/rqlite/rqlite/pull/1760): More use of `atomic` integers.
- [PR #1762](https://github.com/rqlite/rqlite/pull/1762): Boot and Join should be cancelable. Fixes issue [#1746](https://github.com/rqlite/rqlite/issues/1746).

## v8.23.3 (April 23rd 2024)
### Implementation changes and bug fixes
- [PR #1754](https://github.com/rqlite/rqlite/pull/1754): Minor improvements to TCP module code.
- [PR #1755](https://github.com/rqlite/rqlite/pull/1755): `go mod` updates.
- [PR #1757](https://github.com/rqlite/rqlite/pull/1757): Zero retries (by default) for internode communications.
- [PR #1758](https://github.com/rqlite/rqlite/pull/1758): Internode retry count settable by requests. Fixes issue [#1756](https://github.com/rqlite/rqlite/issues/1756).
- [PR #1759](https://github.com/rqlite/rqlite/pull/1759): Improve lock handing in connection pool.

## v8.23.2 (April 22nd 2024)
This release fixes an issue where an uncontactable node could result in delayed requests when communicating with contactable nodes.
### Implementation changes and bug fixes
- [PR #1749](https://github.com/rqlite/rqlite/pull/1749): Load _Queued Writes_ sequence numbers using `atomic`. Thanks @arturmelanchyk
- [PR #1753](https://github.com/rqlite/rqlite/pull/1753): Don't attempt to dial nodes while holding onto Pools lock.

## v8.23.1 (April 5th 2024)
### Implementation changes and bug fixes
- [PR #1732](https://github.com/rqlite/rqlite/pull/1732): Queue now uses generic types.
- [PR #1742](https://github.com/rqlite/rqlite/pull/1742): Log HTTP writer failures.
- [PR #1743](https://github.com/rqlite/rqlite/pull/1743): Move to explicit flag set for command-line parsing.
- [PR #1745](https://github.com/rqlite/rqlite/pull/1745): go mod updates.
- [PR #1682](https://github.com/rqlite/rqlite/pull/1682), [PR #1683](https://github.com/rqlite/rqlite/pull/1683): Move to Go 1.22.

## v8.23.0 (March 14th 2024)
Upgrading to this release can be performed via a rolling restart if necessary. However, until all nodes in a cluster are running v8.23.0, writes to that cluster **might** return an error. Queries should operate without issue during any rolling restart.
### New features
- [PR #1722](https://github.com/rqlite/rqlite/pull/1722), [PR #1727](https://github.com/rqlite/rqlite/pull/1727): Support SQLite `RETURNING` keyword. Fixes issue [#1157](https://github.com/rqlite/rqlite/issues/1157).

### Implementation changes and bug fixes
- [PR #1725](https://github.com/rqlite/rqlite/pull/1725): `go mod` updates.
- [PR #1724](https://github.com/rqlite/rqlite/pull/1724): Allow all SQL parsing to be disabled on a per-request basis.
- [PR #1716](https://github.com/rqlite/rqlite/pull/1716): Miscellaneous code clean-ups.
- [PR #1718](https://github.com/rqlite/rqlite/pull/1718): Support INFO-level logging of Snapshot reaping.
- [PR #1719](https://github.com/rqlite/rqlite/pull/1719): Check if incoming snapshot is later than existing.
- [PR #1720](https://github.com/rqlite/rqlite/pull/1720): Some `RETURNING`-related unit tests.
- [PR #1721](https://github.com/rqlite/rqlite/pull/1721), [PR #1723](https://github.com/rqlite/rqlite/pull/1723): Upgrade SQL parser to bring in `RETURNING` support.

## v8.22.2 (March 2nd 2024)
### Implementation changes and bug fixes
- [PR #1708](https://github.com/rqlite/rqlite/pull/1708): Some more HTTP-level unit tests.
- [PR #1709](https://github.com/rqlite/rqlite/pull/1709): Unit test SQLite keyword `STRICT`.
- [PR #1710](https://github.com/rqlite/rqlite/pull/1710): Unit test querying a hex value. See issue [#1532](https://github.com/rqlite/rqlite/issues/1532).
- [PR #1714](https://github.com/rqlite/rqlite/pull/1714): Don't double-reap Snapshots. Fixes issue [#1711](https://github.com/rqlite/rqlite/issues/1711).
- [PR #1715](https://github.com/rqlite/rqlite/pull/1715): `go mod` updates.

## v8.22.1 (February 27th 2024)
### Implementation changes and bug fixes
- [PR #1706](https://github.com/rqlite/rqlite/pull/1706): Remove obsolete Raft log-related code. Fixes issue [#1705](https://github.com/rqlite/rqlite/issues/1705).

## v8.22.0 (February 26th 2024)
This release adds new support for handling BLOB data. Check out the [documentation](https://rqlite.io/docs/api/api/#blob-data) for more details.
### New features
- [PR #1703](https://github.com/rqlite/rqlite/pull/1703): Support JSON marshaling byte slices as arrays of integers. Fixes issue [#1691](https://github.com/rqlite/rqlite/issues/1691) and [#1345](https://github.com/rqlite/rqlite/issues/1345).
- [PR #1704](https://github.com/rqlite/rqlite/pull/1704): Add rqlite shell support for displaying BLOB data as byte arrays.

### Implementation changes and bug fixes
- [PR #1702](https://github.com/rqlite/rqlite/pull/1702): Add basic BLOB unit testing to DB layer.

## v8.21.3 (February 24th 2024)
### Implementation changes and bug fixes
- [PR #1700](https://github.com/rqlite/rqlite/pull/1700): Accessing non-open Store shouldn't panic. Fixes issue [#1698](https://github.com/rqlite/rqlite/issues/1698).

## v8.21.2 (February 23rd 2024)
### Implementation changes and bug fixes
- [PR #1697](https://github.com/rqlite/rqlite/pull/1697): Use consistent file perms post Boot.

## v8.21.1 (February 21st 2024)
### Implementation changes and bug fixes
- [PR #1693](https://github.com/rqlite/rqlite/pull/1693): Use built-in `max` function for Commit Index _sync_ check.
- [PR #1694](https://github.com/rqlite/rqlite/pull/1694): Correct output of `/readyz` when using _sync_ flag.

## v8.21.0 (February 21st 2024)
This release enhances the `/readyz` check, giving you more information about node readiness. See [the documentation](https://rqlite.io/docs/guides/monitoring-rqlite/#readiness-checks) for more details.
### New features
- [PR #1689](https://github.com/rqlite/rqlite/pull/1689): `/readyz` can wait for Commit Index, via `sync` flag.

### Implementation changes and bug fixes
- [PR #1692](https://github.com/rqlite/rqlite/pull/1692): `go mod` updates.

## v8.20.3 (February 17th 2024)
### Implementation changes and bug fixes
- [PR #1690](https://github.com/rqlite/rqlite/pull/1690): Check for `isTextType` in panic-proof way.

## v8.20.2 (February 16th 2024)
### Implementation changes and bug fixes
- [PR #1685](https://github.com/rqlite/rqlite/pull/1685): Rename a Proto (but not its fields).
- [PR #1686](https://github.com/rqlite/rqlite/pull/1686): Node returns _Meta_, not just Address.
- [PR #1688](https://github.com/rqlite/rqlite/pull/1688): Expose Leader Commit Index, as read from latest AppendEntries RPC.
- [Commit 40e3098](https://github.com/rqlite/rqlite/commit/40e3098e3c7ab1512a6436adac32a7017d24dc4c): Seeing some boot failures locally, revert to default GZIP compression. `git bisect` shows this issue was introduced with [this change](https://github.com/rqlite/rqlite/pull/1574/files#diff-e3c4101b534a442b6f05bbaa9c1c2b9e2f459e92d865ae6654a6ae3d532a7a49).

## v8.20.1 (February 13th 2024)
### Implementation changes and bug fixes
- [PR #1684](https://github.com/rqlite/rqlite/pull/1684): Improvements to strict _Stale Read_ checks.

## v8.20.0 (February 12th 2024)
### New features
- [PR #1681](https://github.com/rqlite/rqlite/pull/1681): Add `freshness_strict` flag, which checks for _Stale Reads_ using Leader time. Thanks @aderouineau

### Implementation changes and bug fixes
- [PR #1670](https://github.com/rqlite/rqlite/pull/1670): Improve error message when query on remote node fails.
- [PR #1671](https://github.com/rqlite/rqlite/pull/1670): Minor optimizations to Unified Request processing.
- [PR #1674](https://github.com/rqlite/rqlite/pull/1674): Small refactor of _Stale Reads_ check.
- [PR #1675](https://github.com/rqlite/rqlite/pull/1675): Use `atomic.Uint64` instead of Mutexes for Store indexes.

## v8.19.0 (February 3rd 2024)
This release allows you to set a maximum amount of a time a query will run. If the query does not complete within the set time, an error will be returned.
### New features
- [PR #1666](https://github.com/rqlite/rqlite/pull/1667), [PR #1667](https://github.com/rqlite/rqlite/pull/1667), [PR #1669](https://github.com/rqlite/rqlite/pull/1669): Support timing out if query doesn't finish within specified interval. Fixes issue [#1657](https://github.com/rqlite/rqlite/issues/1657). Thanks @mauri870

### Implementation changes and bug fixes
- [PR #1665](https://github.com/rqlite/rqlite/pull/1665): Minor improvements to `random` module.

## v8.18.7 (February 1st 2024)
### Implementation changes and bug fixes
- [PR #1663](https://github.com/rqlite/rqlite/pull/1663): Remove unnecessary WAL-close during Raft snapshotting.

## v8.18.6 (January 31st 2024)
### Implementation changes and bug fixes
- [PR #1656](https://github.com/rqlite/rqlite/pull/1656): Add low-level WAL compaction timings and metrics.
- [PR #1660](https://github.com/rqlite/rqlite/pull/1660): Upgrade to SQLite 3.45.1.
- [PR #1659](https://github.com/rqlite/rqlite/pull/1659): Use `go generate` to generate Go Protobuf code. Thanks @mauri870
- [PR #1661](https://github.com/rqlite/rqlite/pull/1661): Jitter the WAL size check interval.

## v8.18.5 (January 30th 2024)
### Implementation changes and bug fixes
- [PR #1646](https://github.com/rqlite/rqlite/pull/1646): Expose BUSY TIMEOUT on /status.
- [PR #1647](https://github.com/rqlite/rqlite/pull/1647): More CHECKPOINT test coverage.
- [PR #1649](https://github.com/rqlite/rqlite/pull/1649): Check Leader when handling `/db/request` with _None_ read consistency. Fixes issue [#1648](https://github.com/rqlite/rqlite/issues/1648).
- [PR #1653](https://github.com/rqlite/rqlite/pull/1653): Fix `busy_timeout` stat for read-only DB. Thanks @mauri870
- [PR #1654](https://github.com/rqlite/rqlite/pull/1654): Memoize SQLite compilation options.

## v8.18.4 (January 30th 2024)
### Implementation changes and bug fixes
- [PR #1644](https://github.com/rqlite/rqlite/pull/1644): Remove an unnecessary memcpy during Snapshotting.

## v8.18.3 (January 29th 2024)
### Implementation changes and bug fixes
- [PR #1638](https://github.com/rqlite/rqlite/pull/1638): More Snapshotting metrics.
- [PR #1639](https://github.com/rqlite/rqlite/pull/1639): Reuse Session and S3 manager when working with AWS S3. Thanks @mauri870
- [PR #1640](https://github.com/rqlite/rqlite/pull/1640): Remove Restart checkpoint, tests show it's not an optimization.
- [PR #1641](https://github.com/rqlite/rqlite/pull/1641): `go mod` updates.

## v8.18.2 (January 27th 2024)
### Implementation changes and bug fixes
- [PR #1635](https://github.com/rqlite/rqlite/pull/1635): Always execute ExecuteRequests locally if possible.
- [PR #1636](https://github.com/rqlite/rqlite/pull/1636): Move to explicit choice of SQLite Checkpointing mode.
- [PR #1637](https://github.com/rqlite/rqlite/pull/1637): Remove unneeded SetFullNeeded post WAL checkpoint failure.

## v8.18.1 (January 26th 2024)
### Implementation changes and bug fixes
- [PR #1633](https://github.com/rqlite/rqlite/pull/1633): Improve error messages for internode communication failures.
- [PR #1634](https://github.com/rqlite/rqlite/pull/1634): FullSnapshot needed if WAL checkpoint fails.

## v8.18.0 (January 25th 2024)
This release upgrades SQLite to 3.45.0, which brings in [JSONB](https://sqlite.org/draft/jsonb.html) support. JSONB is a more efficient way to process JSON data within the SQLite database.
### New features
- [PR #1632](https://github.com/rqlite/rqlite/pull/1632): Upgrade to SQLite 3.45.0.
- [PR #1631](https://github.com/rqlite/rqlite/pull/1631): Allow HTTP clients to control number of retries for internode requests.

### Implementation changes and bug fixes
- [PR #1629](https://github.com/rqlite/rqlite/pull/1629): Set default cluster client retries to 0.

## v8.17.0 (January 22nd 2024)
This release adds the ability to [configure scheduled](https://rqlite.io/docs/guides/performance/#vacuum) [VACUUM](https://www.sqlite.org/lang_vacuum.html) of the SQLite database managed by rqlite. As part of the work for this release, extensive research and testing was performed to confirm that explicitly issuing a `VACUUM` command is also compatible with rqlite. This testing has been made part of the automatic test suite.
### New features
- [PR #1619](https://github.com/rqlite/rqlite/pull/1619), [PR #1622](https://github.com/rqlite/rqlite/pull/1622): Support automatic `VACUUM` of the SQLite database. Fixes [#1609](https://github.com/rqlite/rqlite/issues/1609).

### Implementation changes and bug fixes
- [PR #1623](https://github.com/rqlite/rqlite/pull/1623): Unit tests for Swappable DB.
- [PR #1625](https://github.com/rqlite/rqlite/pull/1625): Count Cluster client retries at operation level.
- [PR #1626](https://github.com/rqlite/rqlite/pull/1626): Unit test explicit VACUUM operation.

## v8.16.8 (January 20th 2024)
### Implementation changes and bug fixes
- [PR #1615](https://github.com/rqlite/rqlite/pull/1615): Add extensive WAL checkpoint test at the database level.
- [PR #1616](https://github.com/rqlite/rqlite/pull/1616): Add time and checksum based change-detection functions to the database level.
- [PR #1617](https://github.com/rqlite/rqlite/pull/1617): Add `VacuumInto` to database layer.
- [PR #1621](https://github.com/rqlite/rqlite/pull/1621): Fix a panic in the rqlite shell by not stomping on an "outer" error.

## v8.16.7 (January 18th 2024)
The releases changes the default logging level for the Raft subsystem from `INFO` to `WARN`. This results is less logging by the Raft subsystem. If you prefer the previous `INFO` level of logging, it can be re-enabled via the command line flag `-raft-log-level=INFO`.
### Implementation changes and bug fixes
- [PR #1607](https://github.com/rqlite/rqlite/pull/1607): Remove use of deprecated `ioutil`.
- [PR #1608](https://github.com/rqlite/rqlite/pull/1608): Always close the FSM Snapshot.
- [PR #1610](https://github.com/rqlite/rqlite/pull/1610): Change Raft default log level to `WARN`.
- [PR #1611](https://github.com/rqlite/rqlite/pull/1611): Don't log incremental Raft snapshots.
- [PR #1612](https://github.com/rqlite/rqlite/pull/1612): `go mod` updates.

## v8.16.6 (January 16th 2024)
### Implementation changes and bug fixes
- [PR #1603](https://github.com/rqlite/rqlite/pull/1603): Standardize logging by Raft module.
- [PR #1604](https://github.com/rqlite/rqlite/pull/1604), [PR #1605](https://github.com/rqlite/rqlite/pull/1605), [PR #1606](https://github.com/rqlite/rqlite/pull/1606): Minor refactor of database code.
- [Commit 2176101](https://github.com/rqlite/rqlite/commit/21761011d45630998ea603576d5c390bafba0afd): Fix rqlite shell help output.

## v8.16.5 (January 14th 2024)
This release further improves _Automatic Backup_ performance, as well as improving test coverage generally.
### Implementation changes and bug fixes
- [PR #1592](https://github.com/rqlite/rqlite/pull/1592): Refactor and enhance upload logging.
- [PR #1593](https://github.com/rqlite/rqlite/pull/1593): Tighten snapshot-join end-to-end testing.
- [PR #1596](https://github.com/rqlite/rqlite/pull/1596): Track Raft logs which change the database.
- [PR #1597](https://github.com/rqlite/rqlite/pull/1597): Clarify end-to-end testing code.
- [PR #1598](https://github.com/rqlite/rqlite/pull/1598): Refactor Store-level index tracking.
- [PR #1599](https://github.com/rqlite/rqlite/pull/1599): Test no upload after Leader change.
- [PR #1600](https://github.com/rqlite/rqlite/pull/1600): Use Raft index for upload checks. Fixes [#1594](https://github.com/rqlite/rqlite/issues/1594).
- [PR #1601](https://github.com/rqlite/rqlite/pull/1601): CREATE TABLE should change DB Applied index.
- [PR #1602](https://github.com/rqlite/rqlite/pull/1602): `go mod` updates.

## v8.16.4 (January 12th 2024)
This release improves _Automatic Backup_ performance, mostly by avoiding unnecessary file copies and uploads.
### Implementation changes and bug fixes
- [PR #1584](https://github.com/rqlite/rqlite/pull/1584): Count Snapshot reaping failures.
- [PR #1585](https://github.com/rqlite/rqlite/pull/1585): Avoid unnecessary auto-backups by storing sha256 sums in S3. Fixes issue [#1565](https://github.com/rqlite/rqlite/issues/1565).
- [PR #1586](https://github.com/rqlite/rqlite/pull/1586): Auto-backups will be in WAL mode going forward, and not in DELETE mode.
- [PR #1587](https://github.com/rqlite/rqlite/pull/1587): Refactor Store Backup Provider to use `io.Writer`.
- [PR #1588](https://github.com/rqlite/rqlite/pull/1588): More consistent use of Sum types in Uploader.
- [PR #1589](https://github.com/rqlite/rqlite/pull/1589): Avoid SQLite file copy during automatic backups.
- [PR #1590](https://github.com/rqlite/rqlite/pull/1590): Fix automatic backup end-to-end tests.

## v8.16.3 (January 9th 2024)
### Implementation changes and bug fixes
- [PR #1582](https://github.com/rqlite/rqlite/pull/1582): Explicitly switch any upgraded v7 Snapshot to WAL mode.
- [PR #1583](https://github.com/rqlite/rqlite/pull/1583): Loading a database invalidates existing snapshots. Fixes [#1583](https://github.com/rqlite/rqlite/issues/1583).

## v8.16.2 (January 9th 2024)
This releases fixes a bug related to Raft snapshot management. While it's an edge case, and can only happen if rqlited is hard-killed at a very specific point, all 8.x users should upgrade to this release.
### Implementation changes and bug fixes
- [PR #1580](https://github.com/rqlite/rqlite/pull/1580): List newest Snapshot, not oldest.

## v8.16.1 (January 8th 2024)
### Implementation changes and bug fixes
- [PR #1574](https://github.com/rqlite/rqlite/pull/1574): Use "GZIP best speed" for internode traffic compression.
- [PR #1575](https://github.com/rqlite/rqlite/pull/1575): Upload Provider uses Snapshot-locking backup.
- [PR #1576](https://github.com/rqlite/rqlite/pull/1576): Add fast path for vacuumed, non-compressed backups.
- [PR #1579](https://github.com/rqlite/rqlite/pull/1579): Only run auto-backups on Leader (as per docs) and improve check efficiency.
- [PR #1578](https://github.com/rqlite/rqlite/pull/1578): Don't require static credentials for S3 access. Thanks @jtackaberry

## v8.16.0 (January 6th 2024)
### New features
- [PR #1563](https://github.com/rqlite/rqlite/pull/1563): Support S3-compatible storage systems for auto-backups and auto-restores. Fixes issue [#1560](https://github.com/rqlite/rqlite/issues/1560). Thanks @jtackaberry
- [PR #1573](https://github.com/rqlite/rqlite/pull/1573): Add support for automatically gzipped-compressed backups.

### Implementation changes and bug fixes
- [PR #1567](https://github.com/rqlite/rqlite/pull/1567): Refactor to make more use of `progress` module.
- [Commit d1cc802](https://github.com/rqlite/rqlite/commit/d1cc80229221ff51cd4741cc7a2e05e87f0337cb): Fix return codes in `HasData()`.
- [PR #1566](https://github.com/rqlite/rqlite/pull/1566): Move some Store state-related functions to own file.
- [PR #1570](https://github.com/rqlite/rqlite/pull/1570): Support compressed backups at the `Store` level.
- [PR #1571](https://github.com/rqlite/rqlite/pull/1571): Stream backups efficiently from remote nodes.
- [PR #1572](https://github.com/rqlite/rqlite/pull/1572): Allow booting with WAL-mode SQLite files.

## v8.15.0 (January 4th 2024)
This release fixes bugs related to auto-restore from S3, improves backup performance, and adds some other minor enhancements.
### New features
- [PR #1550](https://github.com/rqlite/rqlite/pull/1550): CLI command `.nodes` supports showing non-voting nodes.

### Implementation changes and bug fixes
- [PR #1548](https://github.com/rqlite/rqlite/pull/1548): Make system-level test failures easier to understand.
- [PR #1555](https://github.com/rqlite/rqlite/pull/1555): Correct build and import of Protobuf files.
- [PR #1556](https://github.com/rqlite/rqlite/pull/1556): Add fast-path backup.
- [PR #1556](https://github.com/rqlite/rqlite/pull/1556): rqlite CLI streams backup to file.
- [PR #1557](https://github.com/rqlite/rqlite/pull/1557): Remove restriction on restores using SQLite files in WAL mode.
- [PR #1564](https://github.com/rqlite/rqlite/pull/1564): Only auto-restore if the node is "empty". Fixes issue [#1561](https://github.com/rqlite/rqlite/issues/1561). Thanks @jtackaberry

## v8.14.1 (December 31st 2023)
### Implementation changes and bug fixes
- [PR #1546](https://github.com/rqlite/rqlite/pull/1546): Don't hardcode suffrage when joining. Fixes issue [#1545](https://github.com/rqlite/rqlite/issues/1545). Thanks @jtackaberry

## v8.14.0 (December 31st 2023)
This release adds new control over Raft snapshotting, a key part of the Raft consensus protocol. When the WAL file reaches a certain size (4MB by default, which equals the SQLite default), rqlite will trigger a Raft snapshot. In its default setting this change may reduce disk usage, but may also result in more frequent Raft snapshotting. Most users can ignore this change and carry on as before after upgrading to this release.
### New features
- [PR #1530](https://github.com/rqlite/rqlite/pull/1530), [PR #1533](https://github.com/rqlite/rqlite/pull/1533): Support automatically snapshotting when WAL reaches the SQLite default of 4MB.
- [PR #1541](https://github.com/rqlite/rqlite/pull/1541), [PR #1542](https://github.com/rqlite/rqlite/pull/1542): DNS-based autoclustering supports read-only (non-voting) nodes. Fixes issue [#1521](https://github.com/rqlite/rqlite/issues/1521)
- [PR #1544](https://github.com/rqlite/rqlite/pull/1544): Support autoclustering of read-only nodes with Consul and etcd.

### Implementation changes and bug fixes
- [PR #1531](https://github.com/rqlite/rqlite/pull/1531): Check for Raft snapshot condition every 10 seconds by default.
- [PR #1528](https://github.com/rqlite/rqlite/pull/1528): Support setting trailing logs for user-requested snapshot.
- [PR #1529](https://github.com/rqlite/rqlite/pull/1529): Remove obsolete code related to user-triggered snapshots.
- [PR #1536](https://github.com/rqlite/rqlite/pull/1536): Store WAL path in store, to avoid races.
- [PR #1535](https://github.com/rqlite/rqlite/pull/1535): Refactor using CommandProcessor.
- [PR #1539](https://github.com/rqlite/rqlite/pull/1539): `go mod` updates.
- [PR #1540](https://github.com/rqlite/rqlite/pull/1540): Friendlier display of database sizes.
- [PR #1543](https://github.com/rqlite/rqlite/pull/1543): Remove some excessive logging.

## v8.13.5 (December 26th 2023)
### Implementation changes and bug fixes
- [PR #1522](https://github.com/rqlite/rqlite/pull/1522): Minor refactoring of main module.
- [PR #1523](https://github.com/rqlite/rqlite/pull/1523): Move download functionality into _restore_ module.
- [PR #1524](https://github.com/rqlite/rqlite/pull/1524): Disco mode not supported when explicitly joining.
- [PR #1525](https://github.com/rqlite/rqlite/pull/1525): Make Store _Notify_ logic clearer.
- [PR #1526](https://github.com/rqlite/rqlite/pull/1526): Bootstrapper explicitly supports Voting nodes.
- [PR #1527](https://github.com/rqlite/rqlite/pull/1527): More snapshotting instrumentation.

## v8.13.4 (December 23rd 2023)
This release makes sure the version information is correctly recorded in the released binaries. There are no functional changes.
### Implementation changes and bug fixes
- [Commit 03b6db2](https://github.com/rqlite/rqlite/commit/03b6db2e7dd0e6806b1315eb1cd63e04b126a235): Fix build process so versioning information is set correctly.

## v8.13.3 (December 23rd 2023)
### Implementation changes and bug fixes
- [PR #1515](https://github.com/rqlite/rqlite/pull/1515): Fix a log message related to mutual TLS.
- [PR #1516](https://github.com/rqlite/rqlite/pull/1516): Add support to Python end-to-end test helpers for mTLS.
- [PR #1518](https://github.com/rqlite/rqlite/pull/1518): Refactor muxed internode communications.
- [PR #1519](https://github.com/rqlite/rqlite/pull/1519): Refactor TCP TLS configuration control.
- [PR #1520](https://github.com/rqlite/rqlite/pull/1520): End-to-end testing of setting TLS _ServerName_. Confirms that [issue #1507](https://github.com/rqlite/rqlite/issues/1507) is fixed.

## v8.13.2 (December 21st 2023)
### Implementation changes and bug fixes
- [PR #1512](https://github.com/rqlite/rqlite/pull/1512): Fix swapping of CACert and ServerName.

## v8.13.1 (December 21st 2023)
### Implementation changes and bug fixes
- [PR #1510](https://github.com/rqlite/rqlite/pull/1510): Remove obsolete `-http-no-verify` command-line flag.
- [PR #1511](https://github.com/rqlite/rqlite/pull/1511): Bring use of `go mod` into compliance. Fixes [issue #644](https://github.com/rqlite/rqlite/issues/644).

## v8.13.0 (December 21st 2023)
This release supports setting the _Server Name_ a node should expect in any certificate it receives from another node in the cluster.
### New features
- [PR #1509](https://github.com/rqlite/rqlite/pull/1509): Support setting the Server Name for internode certificate verification. Fixes [issue #1507](https://github.com/rqlite/rqlite/issues/1507).

### Implementation changes and bug fixes
- [PR #1503](https://github.com/rqlite/rqlite/pull/1503): Use SQLite-style help in rqlite shell.
- [PR #1505](https://github.com/rqlite/rqlite/pull/1505): Correct handling of IPv6 addresses in rqlite shell.

## v8.12.3 (December 19th 2023)
### Implementation changes and bug fixes
- [PR #1502](https://github.com/rqlite/rqlite/pull/1502): Create temporary SQLite files in same directory as actual SQLite file.

## v8.12.2 (December 19th 2023)
### Implementation changes and bug fixes
- [PR #1498](https://github.com/rqlite/rqlite/pull/1498): rqlite shell `.help` should show commands in alphabetical order.
- [PR #1499](https://github.com/rqlite/rqlite/pull/1499): Bump golang.org/x/crypto from v0.16.0 to v0.17.0.
- [PR #1501](https://github.com/rqlite/rqlite/pull/1501): Upgrade rqlite disco-client to handle IPv6 addresses. Fixes [issue #1500](https://github.com/rqlite/rqlite/issues/1500). Thanks @jtackaberry

## v8.12.1 (December 18th 2023)
### Implementation changes and bug fixes
- [PR #1497](https://github.com/rqlite/rqlite/pull/1497): Don't re-open and close database on shutdown. It's unnecessary.

## v8.12.0 (December 17th 2023)
This version sees the minor version incremented to indicate the importance of this release. Bcrypted passwords were not secure in the Credentials Configuration, as they could also be used directly as passwords. This has been fixed, and bcrypted passwords are no longer supported going forward. **All users using bcrypted hashes in Credential files should upgrade to this release** and migrate to using plaintext passwords in those files.

If you were using bcrypted passwords, **this is probably a breaking change**. You should recreate any Credentials Configuration files to use plaintext passwords instead of bcrypt hashes, and ensure the Credentials Configuration files are secured from unauthorized access.

### Implementation changes and bug fixes
- [PR #1492](https://github.com/rqlite/rqlite/pull/1492): Remove faulty bcrypt hashed password support. Fixes [issue #1488](https://github.com/rqlite/rqlite/issues/1488). Thanks @jtackaberry
- [PR #1494](https://github.com/rqlite/rqlite/pull/1494): Confirm restored data looks like a SQLite file.

## v8.11.1 (December 17th 2023)
### Implementation changes and bug fixes
- [PR #1490](https://github.com/rqlite/rqlite/pull/1490): Guard against `nil` History in rqlite shell. Fixes [issue #1486](https://github.com/rqlite/rqlite/issues/1486).

## v8.11.0 (December 17th 2023)
### New features
- [PR #1489](https://github.com/rqlite/rqlite/pull/1489): Add `.boot` command to rqlite shell, to support _Booting_ nodes.

### Implementation changes and bug fixes
- [PR #1487](https://github.com/rqlite/rqlite/pull/1487): Small improvements to rqlite shell.

## v8.10.0 (December 17th 2023)
This release introduces a new, high-performance, initialize-from-SQLite option. Known as _Boot_ loading, it allows an rqlite node to be seeded with large (multi-GB) datasets, with the time taken to seed the node determined only by your disk performance.

### New features
- [PR #1485](https://github.com/rqlite/rqlite/pull/1485): Add Boot loading.

### Implementation changes and bug fixes
- [PR #1484](https://github.com/rqlite/rqlite/pull/1484): Remove ability to trigger chunked-loading.

## v8.0.6 (December 12th 2023)
Release v8.0.6 protects against a malformed database being loaded as a result of using `/db/load`. **All 8.x users should upgrade to this release**.
### Implementation changes and bug fixes
- [PR #1482](https://github.com/rqlite/rqlite/pull/1482): Don't load an invalid database.

## v8.0.5 (December 12th 2023)
### Implementation changes and bug fixes
- [PR #1481](https://github.com/rqlite/rqlite/pull/1481): Revert to simpler one-shot load for SQLite files.

## v8.0.4 (December 12th 2023)
### Implementation changes and bug fixes
- [PR #1471](https://github.com/rqlite/rqlite/pull/1471), [PR #1472](https://github.com/rqlite/rqlite/pull/1472): Refactor query parameters into own code.
- [PR #1473](https://github.com/rqlite/rqlite/pull/1471): `go mod` updates.
- [PR #1478](https://github.com/rqlite/rqlite/pull/1478): Upgrade Go to 1.21 in `go.mod`. Fixes [issue #1476](https://github.com/rqlite/rqlite/issues/1476).
- [PR #1475](https://github.com/rqlite/rqlite/pull/1475): Minor rqlite CLI improvements.
- [PR #1480](https://github.com/rqlite/rqlite/pull/1480): Don't completely truncate the log, due to apparent unsigned overflow issues in Raft log.

## v8.0.3 (December 11th 2023)
### Implementation changes and bug fixes
- [PR #1466](https://github.com/rqlite/rqlite/pull/1466): Close all dechunkers at Store shutdown.
- [PR #1467](https://github.com/rqlite/rqlite/pull/1467): Introduce explicit FSM type.
- [PR #1468](https://github.com/rqlite/rqlite/pull/1468), [PR #1469](https://github.com/rqlite/rqlite/pull/1469): Fix failure-to-restart issue after chunked loading.

## v8.0.2 (December 10th 2023)
Fix an edge case related to Raft Snapshotting when a chunked load is in progress at the same time.
### Implementation changes and bug fixes
- [PR #1456](https://github.com/rqlite/rqlite/pull/1459): Standardize on chunk size.
- [PR #1456](https://github.com/rqlite/rqlite/pull/1459): Set `TrailingLogs=0` to truncate log during user-initiated Snapshotting.
- [PR #1462](https://github.com/rqlite/rqlite/pull/1462): Refactor redirect logic in HTTP service.
- [PR #1463](https://github.com/rqlite/rqlite/pull/1463): Synchronize Snapshotting and chunked loading.
- [PR #1464](https://github.com/rqlite/rqlite/pull/1464): Handle snapshotting of empty WAL files.
- [PR #1465](https://github.com/rqlite/rqlite/pull/1465): Move uploader goroutine into Uploader.

## v8.0.1 (December 8th 2023)
This release fixes an edge case issue during restore-from-SQLite. It's possible if a rqlite system crashes shortly after restoring from SQLite it may not have loaded the data correctly.

### Implementation changes and bug fixes
- [PR #1456](https://github.com/rqlite/rqlite/pull/1456): Wrap Snapshot Store _FullNeeded_ logic in a function.
- [PR #1457](https://github.com/rqlite/rqlite/pull/1457): Allow FullNeeded to be explicitly set to true.
- [PR #1458](https://github.com/rqlite/rqlite/pull/1458): Perform full snapshot after chunked load.

## v8.0.0 (December 5th 2023)
This release introduces support for much larger data sets. Previously the [Raft snapshotting](https://raft.github.io/) process became more memory intensive and time-consuming as the SQLite database became larger. This set an practical upper limit on the size of the SQLite database. With the 8.0 release rqlite has been fundamentally redesigned such that snapshotting consumes approximately the same amount of resources, regardless of the size of the SQLite database.

This release also eases operations, as well as adding new features and bug fixes.

### Upgrading from the 7.x release

Release 8.0 supports (mostly) seamless upgrades from the 7.x series, and upgrading from 7.x has been tested. However, it is still strongly recommended you backup any production cluster before attempting an upgrade. A more conservative approach would be to create a brand new 8.0 system, and load your backup into that cluster. Then switch production traffic over to the new 8.0 cluster.

8.0 and 7.x nodes should be able to interoperate, so a rolling upgrade should work fine **as long as all nodes are fully caught up with the Leader node**. Note you also cannot join a new 8.x node to a preexisting 7.x cluster. Otherwise upgrade should operate but, again, it is strongly recommended you test this first. It is also not recommended that you run a cluster with a mix of 7.x and 8.0 code for any significant length of time, just the time required for a rolling upgrade.

Important things to note if you decide to upgrade an existing 7.x system:
- Backup your 7.x cluster first.
- it is strongly recommended you upgrade your 7.x cluster to the [7.21.4](https://github.com/rqlite/rqlite/releases/tag/v7.21.4) release before upgrading to the 8.0 series.
- 8.0 always runs with an on-disk database, in-memory databases are no longer supported. Improvements made late in the 7.0 series mean there is little difference in write performance between in-memory and on-disk modes, but supporting both modes just meant confusion and higher development costs. If you were previously running in in-memory mode (the previous default), you don't need to do anything. But if you were previously passing `-on-disk` to `rqlited` so that rqlite ran in on-disk mode, you must now remove that flag.
- When forming a new cluster using 8.0, pass the **Raft** address of the remote node to the `-join` command, not the HTTP API address. If your cluster is already formed, upgrades will work without changing anything (`-join` options are ignored if nodes are already members of a cluster). You may need to change any scripting or automatic-configuration generation however.
- Bcrypted password hashes are no longer supported, due to security flaws in the 7.x release. You should regenerate any [Credentials file](https://rqlite.io/docs/guides/security/), and use plaintext passwords only (and prevent unauthorized access to the Credentials file).
- A few rarely, if ever, used `rqlited` command-line flags have been removed. These flags just added operational overhead, while adding little value.

### New features
- [PR #1362](https://github.com/rqlite/rqlite/pull/1362): Enable SQLite [FTS5](https://www.sqlite.org/fts5.html). Fixes [issue #1361](https://github.com/rqlite/rqlite/issues/1361)
- [PR #1405](https://github.com/rqlite/rqlite/pull/1405): Support a configurable HTTP connection timeout in the rqlite CLI. Thanks @jtarchie
- [PR #1418](https://github.com/rqlite/rqlite/pull/1418): Add basic CORS support. Fixes [issue #687](https://github.com/rqlite/rqlite/issues/687). Thanks @kkoreilly
- [PR #1422](https://github.com/rqlite/rqlite/pull/1422): Add mTLS support to rqlite CLI. Fixes [issue #1421](https://github.com/rqlite/rqlite/issues/1421)
- [PR #1427](https://github.com/rqlite/rqlite/pull/1427): Upgrade to SQLite 3.44.0.
- [PR #1433](https://github.com/rqlite/rqlite/pull/1433): Support an optional better form for the `nodes/` output. Fixes [issue #1415](https://github.com/rqlite/rqlite/issues/1415)
- [PR #1447](https://github.com/rqlite/rqlite/pull/1447): Remove-on-shutdown now supports authentication.
- [PR #1451](https://github.com/rqlite/rqlite/pull/1451): Support optional `VACUUM` of SQLite database file before upload to Cloud storage.
- [PR #1452](https://github.com/rqlite/rqlite/pull/1452): Support optional `VACUUM` of requested backup SQLite file.
  
### Implementation changes and bug fixes
- [PR #1368](https://github.com/rqlite/rqlite/pull/1374): Switch to always-on expvar and pprof.
- [PR #1337](https://github.com/rqlite/rqlite/pull/1337): Store can now load from an io.Reader.
- [PR #1339](https://github.com/rqlite/rqlite/pull/1339), [PR #1340](https://github.com/rqlite/rqlite/pull/1340), [PR #1341](https://github.com/rqlite/rqlite/pull/1341): Add `LoadRequest` chunker/dechunker.
- [PR #1343](https://github.com/rqlite/rqlite/pull/1343): Remove previously-obsoleted supported command-line options.
- [PR #1342](https://github.com/rqlite/rqlite/pull/1342): Integrate chunked-loading, applying to auto-restore from the Cloud.
- [PR #1347](https://github.com/rqlite/rqlite/pull/1347): Migrate HTTP layer to chunked loading.
- [PR #1355](https://github.com/rqlite/rqlite/pull/1355): Database layer can run an integrity check.
- [PR #1385](https://github.com/rqlite/rqlite/pull/1358): Remove support for in-memory databases.
- [PR #1360](https://github.com/rqlite/rqlite/pull/1360): 'go mod' updates, and move to go 1.21.
- [PR #1369](https://github.com/rqlite/rqlite/pull/1369), [PR #1370](https://github.com/rqlite/rqlite/pull/1370): Use singleton, sync'ed, random source.
- [PR #1367](https://github.com/rqlite/rqlite/pull/1367): Move to a WAL-based Snapshot store, which unlocks support for much larger data set support.
- [PR #1373](https://github.com/rqlite/rqlite/pull/1373): Remove compression-control command-line options.
- [PR #1377](https://github.com/rqlite/rqlite/pull/1377): Automatically upgrade 7.x snapshots.
- [PR #1380](https://github.com/rqlite/rqlite/pull/1380): Compress snapshots when transmitting over the network.
- [PR #1382](https://github.com/rqlite/rqlite/pull/1382), [PR #1383](https://github.com/rqlite/rqlite/pull/1383): Add basic stats for Snapshot store.
- [PR #1384](https://github.com/rqlite/rqlite/pull/1384): Use less-racy function to retrieve Leader Address and ID.
- [PR #1386](https://github.com/rqlite/rqlite/pull/1386): Ensure full sync'ing and closing of files during WAL replay.
- [PR #1388](https://github.com/rqlite/rqlite/pull/1388): Ensure databases open with WAL checkpoint disabled. Thanks @benbjohnson.
- [PR #1390](https://github.com/rqlite/rqlite/pull/1390): Add Restore functions to Snapshot Store.
- [PR #1394](https://github.com/rqlite/rqlite/pull/1394): Use only one RW database connection.
- [PR #1395](https://github.com/rqlite/rqlite/pull/1395): More DB-level and Snapshotting statistics.
- [PR #1399](https://github.com/rqlite/rqlite/pull/1399): Better trailing flags error message.
- [PR #1404](https://github.com/rqlite/rqlite/pull/1404): Add an interface between Store and Snapshot Store.
- [PR #1410](https://github.com/rqlite/rqlite/pull/1410), [PR #1412](https://github.com/rqlite/rqlite/pull/1412): Implement simpler WAL-based snapshotting.
- [PR #1413](https://github.com/rqlite/rqlite/pull/1413): Remove `-raft-no-freelist-sync` command line flag.
- [PR #1420](https://github.com/rqlite/rqlite/pull/1420), [PR #1431](https://github.com/rqlite/rqlite/pull/1431): Nodes join a cluster using the Raft address, not the HTTP API.
- [PR #1426](https://github.com/rqlite/rqlite/pull/1426): 'go mod' updates, including moving to Raft 1.6.
- [PR #1430](https://github.com/rqlite/rqlite/pull/1430): Check that any supplied Join addresses are not HTTP servers.
- [PR #1437](https://github.com/rqlite/rqlite/pull/1437), [PR #1438](https://github.com/rqlite/rqlite/pull/1438), [PR #1439](https://github.com/rqlite/rqlite/pull/1439): Actually timeout if needed during `nodes/` access. Fixes [issue #1435](https://github.com/rqlite/rqlite/issues/1435). Thanks @dwco-z
- [PR #1440](https://github.com/rqlite/rqlite/pull/1440): Add a Compacting WAL rewriter. Thanks @benbjohnson.
- [PR #1441](https://github.com/rqlite/rqlite/pull/1441), [PR #1443](https://github.com/rqlite/rqlite/pull/1443): Integrate Compacting WAL writer
- [PR #1444](https://github.com/rqlite/rqlite/pull/1444): Trivial clean-ups related to backups.
- [PR #1445](https://github.com/rqlite/rqlite/pull/1445): Count Snapshot upgrades.

## v7.21.4 (July 8th 2023)
### Implementation changes and bug fixes
- [PR #1336](https://github.com/rqlite/rqlite/pull/1336): Remove on-disk-startup control. It's no longer needed as on-disk performance is now very close to in-memory performance, thanks to the switch to _synchronous off_ mode and the use of the SQLite WAL.

## v7.21.3 (July 7th 2023)
### Implementation changes and bug fixes
- [PR #1329](https://github.com/rqlite/rqlite/pull/1329): Try a different version of V2 Snapshot codec.
- [PR #1332](https://github.com/rqlite/rqlite/pull/1332): Upgrade dependencies.
- [PR #1333](https://github.com/rqlite/rqlite/pull/1333): Set "types" for expressions e.g. `COUNT`. Fixes [issue #1330](https://github.com/rqlite/rqlite/issues/1330)

## v7.21.2 (July 1st 2023)
### Implementation changes and bug fixes
- [PR #1321](https://github.com/rqlite/rqlite/pull/1321): Check for errors in responses during load testing.
- [PR #1323](https://github.com/rqlite/rqlite/pull/1323): Add codec for v2 snapshots.
- [PR #1324](https://github.com/rqlite/rqlite/pull/1324): Close Snapshot after we're finished restoring from it.
- [PR #1325](https://github.com/rqlite/rqlite/pull/1325): Handle getting an error when asking for database stats.

## v7.21.1 (June 26th 2023)
This release changes the mode of SQLite, when rqlite is running in _on-disk_ mode. SQLite now runs in WAL mode, when previously it was in DELETE mode. Testing shows this results in a ~30% increase in write-performance.

### Implementation changes and bug fixes
- [PR #1314](https://github.com/rqlite/rqlite/pull/1314): More preparations for WAL mode when running on-disk.
- [PR #1315](https://github.com/rqlite/rqlite/pull/1315), [PR #1316](https://github.com/rqlite/rqlite/pull/1316): Enable WAL when running in on-disk mode.
- [PR #1317](https://github.com/rqlite/rqlite/pull/1317): DB-layer now supports WAL replay.
- [PR #1318](https://github.com/rqlite/rqlite/pull/1318): Periodically record actual applied index. Addresses a possible edge case with on-disk startup.
  
## v7.21.0 (June 20th 2023)
### New features
- [PR #1311](https://github.com/rqlite/rqlite/pull/1311): Support 'key' param on the `/status` HTTP endpoint.
- [PR #1313](https://github.com/rqlite/rqlite/pull/1313): Sysdump now retrieves data from all nodes if possible.

### Implementation changes and bug fixes
- [PR #1309](https://github.com/rqlite/rqlite/pull/1309): Factor Snapshot creation into own module.

## v7.20.6 (June 16th 2023)
### Implementation changes and bug fixes
- [PR #1305](https://github.com/rqlite/rqlite/pull/1305): Upgrade dependencies via `go get`.
- [PR #1306](https://github.com/rqlite/rqlite/pull/1306): Add some (currently unused) WAL control code.
- [PR #1307](https://github.com/rqlite/rqlite/pull/1307), [PR #1308](https://github.com/rqlite/rqlite/pull/1308): Add full WAL-support to database layer. Not yet enabled by full application.

## v7.20.5 (June 14th 2023)
### Implementation changes and bug fixes
- [PR #1302](https://github.com/rqlite/rqlite/pull/1302): Add some important PRAGMA state to database-level status reporting.
- [PR #1303](https://github.com/rqlite/rqlite/pull/1303): Reduce disk space usage by retaining only a single Raft SQLite snapshot.

## v7.20.4 (June 13th 2023)
This release changes the "syncing" mode SQLite uses to _OFF_ when rqlite runs in "on-disk" mode. The [SQLite docs](https://www.sqlite.org/pragma.html#pragma_synchronous) state that this risks database corruption in the event of a crash, but that's a non-issue for rqlite, as rqlite always deletes any SQLite database on startup and rebuilds it from the Raft log. Testing shows this change results in (at least) a 3x speed-up in write performance when operating in "on-disk" mode.

### Implementation changes and bug fixes
- [PR #1301](https://github.com/rqlite/rqlite/pull/1301): Set synchronous mode to `OFF` for SQLite on-disk files.

## v7.20.3 (June 12th 2023)
### Implementation changes and bug fixes
- [PR #1298](https://github.com/rqlite/rqlite/pull/1298): Move FSMSnapshot to own source file.
- [PR #1300](https://github.com/rqlite/rqlite/pull/1300): Check for WAL-enabled SQLite files during load and restore.

## v7.20.2 (June 9th 2023)
### Implementation changes and bug fixes
- [PR #1296](https://github.com/rqlite/rqlite/pull/1296): Use correct connection when checking a SQL statement for "read-only" status, otherwise "database locked" could result. Also refactors much of the DB-level unit tests.

## v7.20.1 (June 1st 2023)
### Implementation changes and bug fixes
- [PR #1291](https://github.com/rqlite/rqlite/pull/1291): Allow bootstrap-join even with preexisting state. Fixes [issue #1290](https://github.com/rqlite/rqlite/issues/1290) 

## v7.20.0 (June 1st 2023)
### New features
- [PR #1288](https://github.com/rqlite/rqlite/pull/1288): Upgrade to SQLite 3.42.0.

### Implementation changes and bug fixes
- [PR #1286](https://github.com/rqlite/rqlite/pull/1286): More validation of passed-in network addresses.

## v7.19.0 (May 23rd 2023)
### New features
- [PR #1278](https://github.com/rqlite/rqlite/pull/1278): Enable support for more CPU architectures. Fixes [issue #901](https://github.com/rqlite/rqlite/issues/901)

### Implementation changes and bug fixes
- [PR #1275](https://github.com/rqlite/rqlite/pull/1275): Node-removal performs retries.
- [PR #1277](https://github.com/rqlite/rqlite/pull/1277): Upgrade dependencies.
- [PR #1279](https://github.com/rqlite/rqlite/pull/1279): Move to custom image to speed up testing on CircleCI.

## v7.18.2 (May 22nd 2023)
### Implementation changes and bug fixes
- [PR #1269](https://github.com/rqlite/rqlite/pull/1269): Add WaitForRemoval() to Store.
- [PR #1270](https://github.com/rqlite/rqlite/pull/1270): Confirm self-removal changes cluster config.
- [PR #1272](https://github.com/rqlite/rqlite/pull/1272): Refactor node self-removal on shutdown.
- [PR #1273](https://github.com/rqlite/rqlite/pull/1273): Make WaitForLeader() more consistent.
- [PR #1274](https://github.com/rqlite/rqlite/pull/1274): Do DNS bootstrapping even if there is preexisting state. Fixes [issue #1247](https://github.com/rqlite/rqlite/issues/1247)

## v7.18.1 (May 20th 2023)
This release also includes some small logging improvements, related to node-shutdown.

### Implementation changes and bug fixes
- [PR #1266](https://github.com/rqlite/rqlite/pull/1266), [PR #1268](https://github.com/rqlite/rqlite/pull/1268): Add network information to `/status`.
- [PR #1267](https://github.com/rqlite/rqlite/pull/1267): Reduce self-remove timeout to 5 seconds.

## v7.18.0 (May 18th 2023)
This release adds a new HTTP endpoint, located at `/db/request`. This endpoint accepts both read and write requests, including mixing both together in a single request. When requests are sent to this endpoint, rqlite will automatically perform the correct operation for each SQL statement in the request. This endpoint may be more convenient for some use cases, and means that client code doesn't have to decide on whether it should send requests to `/db/execute` or `/db/query`. Many thanks to [VOXO](https://voxo.co/) for funding this development.

7.18.0 also includes some small improvements to [diagnostics and instrumentation](https://rqlite.io/docs/guides/monitoring-rqlite/).

### New features
- [PR #1256](https://github.com/rqlite/rqlite/pull/1256), [PR #1258](https://github.com/rqlite/rqlite/pull/1258), [PR #1260](https://github.com/rqlite/rqlite/pull/1260), [PR #1261](https://github.com/rqlite/rqlite/pull/1261), [PR #1265](https://github.com/rqlite/rqlite/pull/1265): Support a _Unified Endpoint_, which can accept both read and write requests. Fixes [issue #263](https://github.com/rqlite/rqlite/issues/263).

## v7.17.0 (May 9th 2023)
### New features
- [PR #1253](https://github.com/rqlite/rqlite/pull/1253): Node optionally removes itself from the cluster automatically when gracefully shutting down. See the [documentation](https://rqlite.io/docs/clustering/general-guidelines/#removing-a-node-automatically-on-shutdown) for full details.

### Implementation changes and bug fixes
- [PR #1252](https://github.com/rqlite/rqlite/pull/1252): Stop the HTTP server first on shutdown.

## v7.16.0 (May 5th 2023)
This release introduces the ability for a node to automatically recover from a backup in AWS S3. See the [documentation](https://rqlite.io/docs/guides/backup/#restoring-from-cloud-storage) for full details.
### New features
- [PR #1243](https://github.com/rqlite/rqlite/pull/1243): Support automatically restoring from AWS S3. Thanks to [VOXO](https://voxo.co/) for funding this development.
- [PR #1244](https://github.com/rqlite/rqlite/pull/1244): Disco configs now support Environment variable expansion.
- [PR #1245](https://github.com/rqlite/rqlite/pull/1245): Support continuing on failure to download from AWS S3.
- [PR #1246](https://github.com/rqlite/rqlite/pull/1246): Add support for custom S3 endpoint.

### Implementation changes and bug fixes
- [PR #1239](https://github.com/rqlite/rqlite/pull/1239): Remove erroneous scaling factor from etcd and Consul reporting service.
- [PR #1240](https://github.com/rqlite/rqlite/pull/1240): Add support for controlling and reading Store readiness.
- [PR #1241](https://github.com/rqlite/rqlite/pull/1241): Check Store is ready in key places.
- [PR #1248](https://github.com/rqlite/rqlite/pull/1248): Refactor autobackup and autorestore.
- [PR #1249](https://github.com/rqlite/rqlite/pull/1249): Retry certain cluster-client operations.

## v7.15.1 (April 29th 2023)
### Implementation changes and bug fixes
- [PR #1233](https://github.com/rqlite/rqlite/pull/1233): Close file handle after upload.

## v7.15.0 (April 28th 2023)
### New features
- [PR #1229](https://github.com/rqlite/rqlite/pull/1229), [PR #1232](https://github.com/rqlite/rqlite/pull/1232): Add support for automatic backups to AWS S3. Many thanks to [VOXO](https://voxo.co/) for funding this development.

## v7.14.3 (April 25th 2023)
### Implementation changes and bug fixes
- [PR #1218](https://github.com/rqlite/rqlite/pull/1218): Check for more possible errors in peers.json. Thanks @Tjstretchalot
- [PR #1220](https://github.com/rqlite/rqlite/pull/1220): Support Notify over Raft connection.
- [PR #1221](https://github.com/rqlite/rqlite/pull/1221): Support Join over Raft connection.
- [PR #1222](https://github.com/rqlite/rqlite/pull/1222): Joiner expands all targets to include protocols.
- [PR #1224](https://github.com/rqlite/rqlite/pull/1224): Fix credentials load error checking. Thanks @phmx
- [PR #1227](https://github.com/rqlite/rqlite/pull/1227): Upgrade dependencies, including moving to [Hashicorp Raft 1.5](https://github.com/hashicorp/raft/pull/541).

## v7.14.2 (April 7th 2023)
This release is the first to includes various bug fixes and optimizations thanks to running much of the code through [Chat GPT-4](https://openai.com/product/gpt-4), most of which are not explicitly listed in the [CHANGELOG](https://github.com/rqlite/rqlite/edit/master/CHANGELOG.md), but you can check the commit history for details. Future releases of rqlite will probably include more such changes.
### Implementation changes and bug fixes
- [PR #1179](https://github.com/rqlite/rqlite/pull/1179): go mod updates.
- [PR #1180](https://github.com/rqlite/rqlite/pull/1180): Support large numbers in requests.
- [PR #1186](https://github.com/rqlite/rqlite/pull/1186): Improve read-only (non-voting) node management. Fixes [issue #1182](https://github.com/rqlite/rqlite/issues/1182).
- [PR #1189](https://github.com/rqlite/rqlite/pull/1189): Migrate to a Protobuf data model for Join Requests.
- [PR #1190](https://github.com/rqlite/rqlite/pull/1190): Migrate to a Protobuf data model for Notify Requests.
- [PR #1207](https://github.com/rqlite/rqlite/pull/1207): Decompose end-to-end testing into distinct CircleCI jobs.
- [PR #1218](https://github.com/rqlite/rqlite/pull/1218): Check for more possible errors in peers.json. Thanks @Tjstretchalot

## v7.14.1 (March 17th 2023)
### Implementation changes and bug fixes
- [PR #1174](https://github.com/rqlite/rqlite/pull/1174): Fix command-line help for x509 resources.
- [PR #1178](https://github.com/rqlite/rqlite/pull/1178): Fix parsing of Named Parameters with `NULL` as value. Fixes [issue #1177](https://github.com/rqlite/rqlite/issues/1177). Thanks @wellescastro

## v7.14.0 (March 8th 2023)
This release sees the addition of mutual TLS support, and corrects some other issues related to the use of TLS and Certificate Authority configuration.

### New features
- [PR #1171](https://github.com/rqlite/rqlite/pull/1171): Support mutual TLS for both HTTP connections and inter-node traffic. See [issue #1167](https://github.com/rqlite/rqlite/issues/1167). Thanks @otto-dev

### Implementation changes and bug fixes
- [PR #1173](https://github.com/rqlite/rqlite/pull/1173): go mod updates.

## v7.13.2 (February 23rd 2023)
### Implementation changes and bug fixes
- [PR #1156](https://github.com/rqlite/rqlite/pull/1156): Better error message when rqlite shell can't connect to a node.
- [PR #1162](https://github.com/rqlite/rqlite/pull/1162): Fix Consul-based discovery issue when using TLS.
- [PR #1163](https://github.com/rqlite/rqlite/pull/1163): go mod updates.

## v7.13.1 (January 6th 2023)
### Implementation changes and bug fixes
- [PR #1146](https://github.com/rqlite/rqlite/pull/1146): Delete history file if `RQLITE_HISTFILESIZE` environment variable is zero. Fixes [issue #1145](https://github.com/rqlite/rqlite/issues/1145). Thanks @jamielinux
- [PR #1148](https://github.com/rqlite/rqlite/pull/1148): go mod updates.

## v7.13.0 (December 15th 2022)
### New features
- [PR #1141](https://github.com/rqlite/rqlite/pull/1141): Store and load CLI history across sessions.

## v7.12.1 (December 7th 2022)
### Implementation changes and bug fixes
- [PR #1135](https://github.com/rqlite/rqlite/pull/1135): Silently ignore self-joins if nothing has changed on the joining node.
- [PR #1136](https://github.com/rqlite/rqlite/pull/1136): Stop HTTP server gracefully on node shutdown.
- [f6c4b17](https://github.com/rqlite/rqlite/commit/f6c4b17a727809696f952a018b2262681932f521): By default, Leader node will stepdown if that node is shutting down.
- [PR #1139](https://github.com/rqlite/rqlite/pull/1139): Cache hashed passwords. Fixes [issue #1138](https://github.com/rqlite/rqlite/issues/1138).
- [PR #1140](https://github.com/rqlite/rqlite/pull/1140): Use SQLite with corrected in-memory database locking ([SQLite forum post](https://sqlite.org/forum/forumpost/d443fb0730)). Fixes [issue #1103](https://github.com/rqlite/rqlite/issues/1103).

## v7.12.0 (December 1st 2022)
### New features
- [PR #1121](https://github.com/rqlite/rqlite/pull/1121): Transparently forward node-removal requests to Leader.
- [PR #1125](https://github.com/rqlite/rqlite/pull/1125): Support fetching a subset of expvar information.
- [PR #1134](https://github.com/rqlite/rqlite/pull/1134): Support stepping down as Leader before shutting down.

### Implementation changes and bug fixes
- [PR #1120](https://github.com/rqlite/rqlite/pull/1120): go mod updates.
- [PR #1126](https://github.com/rqlite/rqlite/pull/1126): Add Queue instrumentation.
- [PR #1127](https://github.com/rqlite/rqlite/pull/1127): Clearer Queued Writes loop logic.
- [PR #1128](https://github.com/rqlite/rqlite/pull/1128): Add ResetStats to some modules.

## v7.11.0 (November 15th 2022)
### New features
- [PR #1114](https://github.com/rqlite/rqlite/pull/1114), [PR #1118](https://github.com/rqlite/rqlite/pull/1118): Support automatically removing non-reachable nodes after a configurable period. Fixes [issue #728](https://github.com/rqlite/rqlite/issues/728).
- [PR #1116](https://github.com/rqlite/rqlite/pull/1116), [PR #1117](https://github.com/rqlite/rqlite/pull/1117): Support associative form for query responses. Fixes [issue #1115](https://github.com/rqlite/rqlite/issues/1115).

## v7.10.1 (November 11th 2022)

### Implementation changes and bug fixes
- [PR #1097](https://github.com/rqlite/rqlite/pull/1097), [PR #1110](https://github.com/rqlite/rqlite/pull/1100): Start HTTP server as soon as possible after launch.
- [PR #1098](https://github.com/rqlite/rqlite/pull/1098): Bootstrapper doesn't need to know the bootstrap-expect value.
- [PR #1099](https://github.com/rqlite/rqlite/pull/1099): Add explicit `.exit` option to CLI.
- [PR #1102](https://github.com/rqlite/rqlite/pull/1102): Use BasicAuth redaction functionality from the standard library.
- [PR #1108](https://github.com/rqlite/rqlite/pull/1108): Add more upgrade testing.
- [PR #1109](https://github.com/rqlite/rqlite/pull/1109): Higher Queued Writes defaults
- [PR #1113](https://github.com/rqlite/rqlite/pull/1113): go mod updates

## v7.10.0 (October 26th 2022)
### New features
- [PR #1096](https://github.com/rqlite/rqlite/pull/1096): Upgrade to SQLite 3.39.4.

### Implementation changes and bug fixes
- [PR #1094](https://github.com/rqlite/rqlite/pull/1094): Update packages to resolve CVE-2022-32149 and CVE-2022-27664. Thanks @sgalsaleh
- [PR #1095](https://github.com/rqlite/rqlite/pull/1095): Log, and add to version output, the SQLite release.
- [PR #1096](https://github.com/rqlite/rqlite/pull/1096): go mod updates.

## v7.9.2 (October 24th 2022)
This release addresses a shortcoming in inter-node communications. Nodes now consistently encode the length of those communications using 8-byte values. **If any node in a cluster is upgraded to this release, then all nodes in that cluster should be**. 

### Implementation changes and bug fixes
- [PR #1089](https://github.com/rqlite/rqlite/pull/1089): Move to 8-byte Protobuf lengths for cluster communications. Fixes [issue #1088](https://github.com/rqlite/rqlite/issues/1088).
- [PR #1090](https://github.com/rqlite/rqlite/pull/1090): Correct error handling for remote load and backup failures.

## v7.9.1 (October 23rd 2022)
### Implementation changes and bug fixes
- [PR #1086](https://github.com/rqlite/rqlite/pull/1086): Restoring via follower should have same HTTP response body.
- [PR #1087](https://github.com/rqlite/rqlite/pull/1087): Notified and joined node checks address resolution.

## v7.9.0 (October 22nd 2022)
This release makes it more convenient to load SQLite files directly into rqlite, as any node can now process the request. For this to work however, all nodes in your cluster must be running v7.9.0 (or later). Otherwise v7.9.0 is fully compatible with earlier release, so a rolling upgrade process is an option.

### New features
- [PR #1084](https://github.com/rqlite/rqlite/pull/1084): Transparently forward SQLite data Restore requests to Leaders.

### Implementation changes and bug fixes
- [PR #1085](https://github.com/rqlite/rqlite/pull/1085): Improved logs during joining.

## v7.8.0 (October 20th 2022)
This release makes it more convenient to retrieve a backup. Now any node can provide a backup of the underlying SQLite database. For this to work however, all nodes in your cluster must be running v7.8.0 (or later). Otherwise v7.8.0 is fully compatible with earlier release, so a rolling upgrade process is an option.

### New features
- [PR #1081](https://github.com/rqlite/rqlite/pull/1081): Transparently forward Backup requests to Leaders.

### Implementation changes and bug fixes
- [PR #1079](https://github.com/rqlite/rqlite/pull/1079): Use a Protobuf model for Backup requests.
- [PR #1078](https://github.com/rqlite/rqlite/pull/1078): Decrease bootstrap polling interval from 5 seconds to 2 seconds.
- [PR #1082](https://github.com/rqlite/rqlite/pull/1082): Small refactor of backup code.

## v7.7.2 (October 14th 2022)
### Implementation changes and bug fixes
- [PR #1075](https://github.com/rqlite/rqlite/pull/1075): Upgrade to latest SQL parser. Fixes [issue #1072](https://github.com/rqlite/rqlite/issues/1072)

## v7.7.1 (October 13th 2022)
### Implementation changes and bug fixes
- [PR #1074](https://github.com/rqlite/rqlite/pull/1074): Support `NULL` as a parameterized value. Fixes [issue #1073](https://github.com/rqlite/rqlite/issues/1073)

## v7.7.0 (September 28th 2022)
This release adds support for SQLite [`RANDOM()`](https://www.sqlite.org/deterministic.html), the first such [support for non-deterministic functions](https://github.com/rqlite/rqlite/blob/master/DOC/NON_DETERMINISTIC_FUNCTIONS.md). It does this via statement-rewriting.

### New features
- [PR #1046](https://github.com/rqlite/rqlite/pull/1046): Add rewriting of SQLite `RANDOM()` so statements with this function are safe to use.

### Implementation changes and bug fixes
- [PR #1064](https://github.com/rqlite/rqlite/pull/1064): Upgrade dependencies, and move to requiring Go 1.18 (or later) for building.

## v7.6.1 (August 7th 2022)

### Implementation changes and bug fixes
- [PR #1058](https://github.com/rqlite/rqlite/pull/1058): `rqlited` terminates if passed unroutable advertised Raft or HTTP addresses.
- [PR #1057](https://github.com/rqlite/rqlite/pull/1057), [PR #1059](https://github.com/rqlite/rqlite/pull/1059): Perform credential checking with intra-cluster communications. Fixes [issue #1051](https://github.com/rqlite/rqlite/issues/1051). Thanks @ngharrington

## v7.6.0 (July 19th 2022)
### New features
- [PR #1055](https://github.com/rqlite/rqlite/pull/1055): Add new `join-read-only` permission.

### Implementation changes and bug fixes
- [PR #1049](https://github.com/rqlite/rqlite/pull/1049): Ignore freshness when serving queries on Leader. Fixes [issue #1048](https://github.com/rqlite/rqlite/issues/1048). Thanks to @Tjstretchalot for the bug report.

## v7.5.1 (June 13th 2022)
### Implementation changes and bug fixes
- [PR #1043](https://github.com/rqlite/rqlite/pull/1043): Allow cluster-connect timeout to be configurable. Fixes [issue #1042](https://github.com/rqlite/rqlite/issues/1042).

## v7.5.0 (May 26th 2022)
This release adds a new, higher-performance, option for writing to the database, known as Queued Writes. This allows users to trade off durability for high-performance writes to the database. See the [documentation](https://github.com/rqlite/rqlite/blob/master/DOC/QUEUED_WRITES.md) for full details.

### New features
- [PR #1019](https://github.com/rqlite/rqlite/pull/1019): CLI supports restoring from SQLite database files.
- [PR #1024](https://github.com/rqlite/rqlite/pull/1024), [PR #1025](https://github.com/rqlite/rqlite/pull/1025), [PR #1031](https://github.com/rqlite/rqlite/pull/1031), [PR #1033](https://github.com/rqlite/rqlite/pull/1033): Add support for Queued Writes. Fixes [issue #1020](https://github.com/rqlite/rqlite/issues/1020).
- [PR #1036](https://github.com/rqlite/rqlite/pull/1036): rqbench supports queued writes.

### Implementation changes and bug fixes
- [PR #1027](https://github.com/rqlite/rqlite/pull/1027): go mod (dependencies) updates, including upgrading SQLite to v3.38.5.
- [PR #1030](https://github.com/rqlite/rqlite/pull/1030), [PR #1032](https://github.com/rqlite/rqlite/pull/1032): Handle more connection errors. Fixes [issue #1029](https://github.com/rqlite/rqlite/issues/1029).

## v7.4.0 (May 10th 2022)
With this release rqlite supports restoring a node from an actual SQLite file, which is very much faster than restoring using the SQL dump representation of the same SQLite database.
### New features
- [PR #1017](https://github.com/rqlite/rqlite/pull/1017), [PR #1018](https://github.com/rqlite/rqlite/pull/1018): Support restoring from SQLite data files. Fixes [issue #1005](https://github.com/rqlite/rqlite/issues/1016).
### Implementation changes and bug fixes
- [PR #1015](https://github.com/rqlite/rqlite/pull/1015): go mod (dependencies) updates.

## v7.3.2 (March 1st 2022)
### Implementation changes and bug fixes
- [PR #999](https://github.com/rqlite/rqlite/pull/999): Add end-to-end encrypted node test.
- [PR #1008](https://github.com/rqlite/rqlite/pull/1008): Upgrade to SQLite 3.38.0. Fixes [issue #1005](https://github.com/rqlite/rqlite/issues/1005).
- [PR #1009](https://github.com/rqlite/rqlite/pull/1009): Don't HTML escape JSON output.

## v7.3.1 (February 6th 2022)
Fixes an issue in the v7.3.0 release that prevented clusters, which used TLS for internode communications, from operating correctly. All deployments using TLS should be upgraded to this version.
### Implementation changes and bug fixes
- [PR #998](https://github.com/rqlite/rqlite/pull/998): Node TLS mux needs to use advertised Raft address. Thanks to [Nathan Ferch](https://github.com/nferch) for the bug report.

## v7.3.0 (February 5th 2022)
With this release rqlite networking is based on whatever network identifiers are passed in at launch. If hostnames are passed they are no longer resolved into IP addresses internally by rqlite, and only the low-level networking layers will do so. This allows rqlite to operate correctly even when cluster node IP addresses change, as long as the hostnames remain the same. This is common in deployment environments such as Kubernetes, particularly when using [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/).

Upgrading an earlier cluster to this release is possible, simply by explicitly setting the IP address of each node at the command line. Alternatively, simply [backup your previous node](https://github.com/rqlite/rqlite/blob/master/DOC/BACKUPS.md) and [restore it](https://github.com/rqlite/rqlite/blob/master/DOC/RESTORE_FROM_SQLITE.md) into a new v7.3.0 node. **In any event, backing up your data is always recommended before any upgrade takes place.**

### New features
- [PR #993](https://github.com/rqlite/rqlite/pull/993): Support IP addresses changing by not explicitly resolving network addresses. Fixes [issue #695](https://github.com/rqlite/rqlite/issues/695), [issue #774](https://github.com/rqlite/rqlite/issues/744), and [issue #991](https://github.com/rqlite/rqlite/issues/991). Thanks to @git001 for help testing this change. 

## v7.2.0 (February 1st 2022)
This release introduces supported for [DNS-based](https://www.cloudflare.com/learning/dns/what-is-dns/) and [DNS SRV -based](https://www.cloudflare.com/learning/dns/dns-records/dns-srv-record/) autoclustering. rqlite can now lookup a DNS record for specified host, and use the network addresses returned to bootstrap the cluster. This can make it much easier to create rqlite clusters using the kinds of Service-Discovery mechanisms you find on Consul and Kubernetes, which are often based on DNS. See the [documentation](https://github.com/rqlite/rqlite/blob/master/DOC/AUTO_CLUSTERING.md) for full details on using DNS-based autoclustering.

### New features
- [PR #979](https://github.com/rqlite/rqlite/pull/979): Add support for DNS-based autoclustering. Fixes [issue #554](https://github.com/rqlite/rqlite/issues/554)
- [PR #985](https://github.com/rqlite/rqlite/pull/985): Add support for DNS SRV -based autoclustering. Fixes [issue #554](https://github.com/rqlite/rqlite/issues/554)

### Implementation changes and bug fixes
- [PR #976](https://github.com/rqlite/rqlite/pull/976): Improve `/readyz` response.
- [PR #978](https://github.com/rqlite/rqlite/pull/978): Return error on join request if node ID is the same as receiving node.
- [PR #980](https://github.com/rqlite/rqlite/pull/980): Move config validation to Config type.
- [PR #981](https://github.com/rqlite/rqlite/pull/981): Add current time to node `/status` output.
- [PR #982](https://github.com/rqlite/rqlite/pull/982): `/readyz` can skip leader check via `noleader` query param.
- [PR #984](https://github.com/rqlite/rqlite/pull/984): Count number of `/status` and `/readyz` requests via expvar.
- [PR #986](https://github.com/rqlite/rqlite/pull/986): Refactor join code with new Joiner type.
- [PR #987](https://github.com/rqlite/rqlite/pull/987): Upgrade to SQLite 3.37.0.

## v7.1.0 (January 28th 2022)
This release introduces a new automatic clustering approach, known as _Bootstrapping_, which allows rqlite clusters to form without assistance from an external system such as Consul. This can be very useful for certain deployment scenarios. See the [documentation](https://github.com/rqlite/rqlite/blob/master/DOC/AUTO_CLUSTERING.md) for full details on using the new Bootstrapping mode. Special thanks to [Nathan Ferch](https://github.com/nferch) for his advice regarding the design and development of this feature.

### New features
- [PR #974](https://github.com/rqlite/rqlite/pull/974): Add support for automatically bootstrapping clusters from just rqlite nodes.

## v7.0.1 (January 26th 2022)
### Implementation changes and bug fixes
- [PR #957](https://github.com/rqlite/rqlite/pull/971): Correct rqlite command line options in log message.
- [PR #973](https://github.com/rqlite/rqlite/pull/973): Use correct JSON field name for Consul disco scheme

## v7.0.0 (January 25th 2022)
This release introduces new node-discovery integration with [Consul](https://www.consul.io/) and [etcd](https://etcd.io/). By using one of those systems with rqlite, automatic clustering of rqlite is much easier. The [legacy Discovery mode](https://github.com/rqlite/rqlite/blob/master/DOC/DISCOVERY.md) is not supported by release 7.0, but may be supported in a future release. So, for now, if you wish to continue using legacy Discovery, you will need to run rqlite 6.x, or earlier.

See the [new documentation](https://github.com/rqlite/rqlite/blob/master/DOC/AUTO_CLUSTERING.md) for full details on using Consul and etcd.

### Upgrading
This release uses a new database for the Raft system, which should be compatible with earlier releases. However it is strongly recommended you [backup any existing Leader nodes](https://github.com/rqlite/rqlite/blob/master/DOC/BACKUPS.md) before you run 7.0, in the event there are any issues.

There are also some breaking changes in release 7.0, related to command-line arguments:
- The disco-related command-line arguments have changed to support Consul and etcd. If you wish to continue to use legacy Discovery, you can't upgrade to 7.0 -- or consider using Consul or etcd for node-discovery.
- The command-line argument `-RaftWaitForLeader` has been removed. If you need to wait for a node to have a Leader, you should poll the `/readyz` endpoint.

### New features
- [PR #957](https://github.com/rqlite/rqlite/pull/957): Support autoclustering via use [Consul](https://www.consul.io/) and [etcd](https://etcd.io/) KV stores.
- [PR #947](https://github.com/rqlite/rqlite/pull/947): CLI takes list of hosts, so it can try another node if first node is unresponsive. Fixes [issue #157](https://github.com/rqlite/rqlite/issues/157). Thanks @chermehdi

### Implementation changes and bug fixes
- [PR #957](https://github.com/rqlite/rqlite/pull/957): Refactor `rqlited` command-line argument code.
- [PR #965](https://github.com/rqlite/rqlite/pull/965): Stop using deprecated protobuf package.
- [PR #967](https://github.com/rqlite/rqlite/pull/967): Replace BoltDB with etcd's fork, [bbolt](https://pkg.go.dev/go.etcd.io/bbolt).
- [PR #968](https://github.com/rqlite/rqlite/pull/968): Control whether bbolt syncs freelist to disk.

## v6.10.2 (January 13th 2022)
### Implementation changes and bug fixes
- [PR #959](https://github.com/rqlite/rqlite/pull/959): Return clearer error if no database results set.

## v6.10.1 (January 13th 2022)
### Implementation changes and bug fixes
- [PR #945](https://github.com/rqlite/rqlite/pull/945): Minor refactor of Store creation.
- [PR #946](https://github.com/rqlite/rqlite/pull/946): Use actual duration types for duration `rqlited` command line flags.
- [PR #944](https://github.com/rqlite/rqlite/pull/944): Refactor how nodes bootstrap.
- [PR #954](https://github.com/rqlite/rqlite/pull/954): Much better random file names.
- [PR #956](https://github.com/rqlite/rqlite/pull/956): Actually return errors from command marshaling code.

## v6.10.0 (January 7th 2022)
This release enhances the authentication and authorization system, making it more convenient to use. It also fixes some minor bugs, and migrates the end-to-end test suite to Python 3.

### New features
- [PR #940](https://github.com/rqlite/rqlite/pull/940): Support specifying the user to join a cluster with, via `-join-as`.
- [PR #940](https://github.com/rqlite/rqlite/pull/940): Add support for pseudo username `*` to authentication configuration, providing more control over access.

### Implementation changes and bug fixes
- [PR #934](https://github.com/rqlite/rqlite/pull/934): Use correct MIME media type for JSON text. Fixes [issue #933](https://github.com/rqlite/rqlite/issues/933).
- [PR #939](https://github.com/rqlite/rqlite/pull/939): Migrate end-to-end testing to Python 3.
- [PR #941](https://github.com/rqlite/rqlite/pull/941): Upgrade go mod dependencies.

## v6.9.0 (December 31st 2021)
### New features
- [PR #932](https://github.com/rqlite/rqlite/pull/932): Add support for named parameters. Fixes [issue #675](https://github.com/rqlite/rqlite/issues/675).

## v6.8.2 (December 2nd 2021)
### Implementation changes and bug fixes
- [PR #929](https://github.com/rqlite/rqlite/pull/929): Support disabling in-memory initialization of on-disk databases. Fixes [issue #928](https://github.com/rqlite/rqlite/issues/928).

## v6.8.1 (November 13th 2021)
### Implementation changes and bug fixes
- [Fix URL](https://github.com/rqlite/rqlite/commit/d8e915e0be589b5cf1d593b80985e8247ba5f3d9) for `.ready` CLI command.
- [PR #925](https://github.com/rqlite/rqlite/pull/925): Ignore disco ID if there is preexisting state. Fixes [issue #347](https://github.com/rqlite/rqlite/issues/347).
- [PR #926](https://github.com/rqlite/rqlite/pull/926): Ignore own join address if passed. Fixes [issue #713](https://github.com/rqlite/rqlite/issues/713).

## v6.8.0 (November 9th 2021)
### New features
- [PR #921](https://github.com/rqlite/rqlite/pull/921): Support fetching `/readyz` via CLI.

### Implementation changes and bug fixes
- [PR #920](https://github.com/rqlite/rqlite/pull/920): Minor log message fixes.
- [PR #922](https://github.com/rqlite/rqlite/pull/922), [PR #924](https://github.com/rqlite/rqlite/pull/924): Fix display of numbers during JSON deserialization. Thanks @tiswong 

## v6.7.0 (October 22nd 2021)
### New features
- [PR #918](https://github.com/rqlite/rqlite/pull/918): Add support for timestamp column types.

### Implementation changes and bug fixes
- [PR #917](https://github.com/rqlite/rqlite/pull/917): Redirect HTTP `/` to `/status`.
- [PR #918](https://github.com/rqlite/rqlite/pull/918): Explicitly handle `nil` type in database layer.

## v6.6.5 (October 21st 2021)
### Implementation changes and bug fixes
- [PR #916](https://github.com/rqlite/rqlite/pull/916): More helpful log messages on start-up.

## v6.6.4 (October 21st 2021)
### Implementation changes and bug fixes
- [PR #915](https://github.com/rqlite/rqlite/pull/915): Record compiler in logs and status output.

## v6.6.3 (October 20th 2021)
This release is the first to statically link `libc` for the Linux version of rqlite. While this does increase the size of binary, one of the main goals of rqlite is ease of deployment. With fully static linking, official releases will run on an even wider range of distributions.

### Implementation changes and bug fixes
- [PR #911](https://github.com/rqlite/rqlite/pull/911): Statically link all requirements, including `libc`, for rqlite on Linux. macOS retains dynamically linking.

## v6.6.2 (October 20th 2021)
### Implementation changes and bug fixes
- [PR #909](https://github.com/rqlite/rqlite/pull/909): Support intra-cluster responses up to 4MB in size. Fixes [issue #908](https://github.com/rqlite/rqlite/issues/908).

## v6.6.1 (October 19th 2021)
### Implementation changes and bug fixes
- [PR #907](https://github.com/rqlite/rqlite/pull/907): Make it clearer when writes are sent to the wrong endpoint. See [issue #903](https://github.com/rqlite/rqlite/issues/903).

## v6.6.0 (September 21st 2021)
### New features
- [PR #898](https://github.com/rqlite/rqlite/pull/898): Support recovering clusters that have permanently lost quorum. Fixes [issue #897](https://github.com/rqlite/rqlite/issues/897).

## v6.5.0 (September 12th 2021)
### New features
- [PR #896](https://github.com/rqlite/rqlite/pull/896): Add `/readyz` endpoint for easy ready-to-respond checks.

### Implementation changes and bug fixes
- [PR #885](https://github.com/rqlite/rqlite/pull/885): Improved responses on HTTP 500.
- [PR #888](https://github.com/rqlite/rqlite/pull/888): Expose stats about BoltDB on the `status/` endpoint.
- [PR #889](https://github.com/rqlite/rqlite/pull/889): Add OS-level information to `status/` output.
- [PR #892](https://github.com/rqlite/rqlite/pull/892): More Snapshot metrics.
- [PR #894](https://github.com/rqlite/rqlite/pull/894): Support timeout on `nodes/` endpoint.
- [PR #895](https://github.com/rqlite/rqlite/pull/895): Start HTTP service before attempting any join operation.

## v6.4.3 (September 8th 2021)
### Implementation changes and bug fixes
- [PR #882](https://github.com/rqlite/rqlite/pull/882): Some minor improvements related to on-disk SQLite use.
- [PR #883](https://github.com/rqlite/rqlite/pull/883): Add missing returns after HTTP errors.
- [PR #884](https://github.com/rqlite/rqlite/pull/884): Serialize on-disk databases by simply reading SQLite file.

## v6.4.2 (September 1st 2021)
### Implementation changes and bug fixes
- [PR #880](https://github.com/rqlite/rqlite/pull/880): Increase maximum in-memory database size to 2GiB, via upgraded dependencies.

## v6.4.1 (August 31st 2021)
### Implementation changes and bug fixes
- [PR #879](https://github.com/rqlite/rqlite/pull/879): Set timeout when fetching node API address.

## v6.4.0 (August 31st 2021)
### New features
- [PR #878](https://github.com/rqlite/rqlite/pull/878): CLI supports setting read consistency level.

### Implementation changes and bug fixes
- [PR #876](https://github.com/rqlite/rqlite/pull/876): Add round-trip time to each node to `nodes/` endpoint output.
- [PR #877](https://github.com/rqlite/rqlite/pull/877): Add Error information to `nodes/` endpoint output.

## v6.3.0 (August 28th 2021)
This release introduces transparent request forwarding, which simplifies interacting with rqlite clusters. Client requests that must be served by the leader will no longer return HTTP 301, and will be forwarded transparently to the leader if necessary. Client software does not need to change to take advantage of this new functionality.

Systems running earlier 6.x software can be upgraded to this release without doing any special, but all nodes in the new cluster must be running this release. This release cannot communicate with nodes running earlier 6.x software.

### New features
- [PR #859](https://github.com/rqlite/rqlite/pull/859): Support transparent Execute and Query request forwarding. Fixes [issue #330](https://github.com/rqlite/rqlite/issues/330).
- [PR #873](https://github.com/rqlite/rqlite/pull/873): Support explicitly specifying SQLite on-disk file path.

### Implementation changes and bug fixes
- [PR #863](https://github.com/rqlite/rqlite/pull/863): Add gauge-like metric for Snapshot timings.
- [PR #854](https://github.com/rqlite/rqlite/pull/864): Use a connection pool for internode communications.
- [PR #867](https://github.com/rqlite/rqlite/pull/867): Add cluster status to Status output.
- [PR #869](https://github.com/rqlite/rqlite/pull/869): Cluster client uses resolved address, and improved status output.

## v6.2.0 (August 18th 2021)
### New features
- [PR #851](https://github.com/rqlite/rqlite/pull/851), [PR #855](https://github.com/rqlite/rqlite/pull/855): rqlite CLI properly supports PRAGMA directives.
- [PR #853](https://github.com/rqlite/rqlite/pull/853): Support enabling Foreign Key constraints via command-line options.

### Implementation changes and bug fixes
- [PR #857](https://github.com/rqlite/rqlite/pull/857): Use Protobufs as core data model.
- [PR #858](https://github.com/rqlite/rqlite/pull/858): Create dedicated client for talking to a cluster service.
- [PR #862](https://github.com/rqlite/rqlite/pull/862): Add detailed SQLite memory statistics to status output.

## v6.1.0 (August 5th 2021)
This release makes significant changes to SQLite database connection handling, resulting in proper support for high-performance concurrent reads of in-memory databases (an in-memory SQLite database is the default option for rqlite). 

### New features
- [PR #848](https://github.com/rqlite/rqlite/pull/848): Enable [DBSTAT](https://www.sqlite.org/dbstat.html) table and [JSON1](https://www.sqlite.org/json1.html) support. Fixes [issue #843](https://github.com/rqlite/rqlite/issues/843).

### Implementation changes and bug fixes
- [PR #841](https://github.com/rqlite/rqlite/pull/841): Remove support for specifying SQLite DSN.
- [PR #842](https://github.com/rqlite/rqlite/pull/842): Use `vfs=memdb` allowing proper concurrent reads of in-memory databases. Special thanks to [@rittneje](https://github.com/rittneje).
- [PR #842](https://github.com/rqlite/rqlite/pull/842): Use read-only database connections for read queries, ensuring write SQL commands are not executed on the wrong endpoint.
- [PR #842](https://github.com/rqlite/rqlite/pull/842): Remove explicit support for Foreign Key constraint control and journal mode. Those controls are best left to the rqlite system now.
- [PR #845](https://github.com/rqlite/rqlite/pull/845): Add SQLite compile-time options to status output.
- [PR #846](https://github.com/rqlite/rqlite/pull/846): New DB and FSM indexes to track state.

## v6.0.2 (July 31st 2021)
This release addresses a significant issue related to SQLite connection handling and multithreading. All users should upgrade to this version.

### Implementation changes and bug fixes
- [PR #827](https://github.com/rqlite/rqlite/pull/827): Upgrade dependencies, including SQLite to 3.36.
- [PR #835](https://github.com/rqlite/rqlite/pull/835): Use Go standard library sql/database abstraction. Fixes [issue #830](https://github.com/rqlite/rqlite/issues/830).
- [PR #835](https://github.com/rqlite/rqlite/pull/835): Use SQLite connection pool and add pool statistics to status output.
- [PR #836](https://github.com/rqlite/rqlite/pull/836): Add current SQLite journal mode to status output.
- [PR #839](https://github.com/rqlite/rqlite/pull/839): Limit in-memory connection pool to 1 connection.
- [PR #840](https://github.com/rqlite/rqlite/pull/840): Upgrade to rqlite/go-sqlite3 v1.20.4. See [this issue](https://github.com/mattn/go-sqlite3/issues/963).

## v6.0.1 (June 28th 2021)
### Implementation changes and bug fixes
- [PR #822](https://github.com/rqlite/rqlite/pull/822): Don't ignore `-join` even if previous state exists. Fixes [issue #818](https://github.com/rqlite/rqlite/issues/818).

## v6.0.0 (June 8th 2021)
This release implements a significant design change, which improves rqlite cluster reliability. With this change a rqlite node can more reliably direct read and write requests to the correct node.

In the 5.0 series, _Follower_ nodes learned the HTTP API address of the cluster Leader via information - known as _Metadata_ - that each node wrote to the Raft log. This Metadata was then available to each node in the cluster, if that node needed to redirect queries to the cluster Leader (assuming that node wasn't the Leader at that time). However that design was somewhat complex, and required the tracking of extra state, in addition to the SQLite database. It also meant that if the Metadata got out of sync with the Raft state, the cluster could be in a degraded state.

In this new design, a node now queries the Leader as needed, when that node needs to learn the Leader's HTTP API address. As a result, the Metadata component has been removed from rqlite, since it is no longer needed. And without any possibility of discrepancy between Metadata and Raft state, a whole class of potential bugs is removed. Any request for the Leader HTTP API address means the requesting node connects to a TCP port already open on the Leader for Raft connections, so does not introduce any new failure modes. This multiplexing of the Raft TCP port is performed via the `mux` package.

This new design does mean that nodes running earlier software cannot communicate with 6.0 nodes, as 6.0 software no longer performs Metadata updates. As a result, **rqlite clusters running 5.x software or earlier must be explicitly upgraded**. To upgrade from an earlier version to this release you should [backup your Leader node](https://github.com/rqlite/rqlite/blob/master/DOC/BACKUPS.md), and [restore the database dump](https://github.com/rqlite/rqlite/blob/master/DOC/RESTORE_FROM_SQLITE.md) into a new 6.0 cluster.

The data API and cluster-management API remain unchanged however, so client code that communicates with rqlite should not need any changes.

### New features
- [PR #796](https://github.com/rqlite/rqlite/pull/796): `nodes/` API reports real-time status of other nodes in cluster. Fixes [issue #768](https://github.com/rqlite/rqlite/issues/768).
- [PR #802](https://github.com/rqlite/rqlite/pull/802): Add `.sysdump` command to rqlite CLI.
- [PR #807](https://github.com/rqlite/rqlite/pull/807): rqlite CLI displays build information. Fixes [issue #768](https://github.com/rqlite/rqlite/issues/806).

### Implementation changes and bug fixes
 - [PR #792](https://github.com/rqlite/rqlite/pull/792): Fetch leader HTTP API addresses on demand.
 - [PR #797](https://github.com/rqlite/rqlite/pull/797): Remove `redirect` key from HTTP status output.

## v5.12.1 (April 29th 2021)

### Implementation changes and bug fixes
 - [PR #791](https://github.com/rqlite/rqlite/pull/791): Reinstate node CA cert support which was erroneously removed in an earlier change.

## v5.12.0 (April 24th 2021)
### New features
 - [PR #788](https://github.com/rqlite/rqlite/pull/788): Upgrade to SQLite 3.35.4.

### Implementation changes and bug fixes
 - [PR #790](https://github.com/rqlite/rqlite/pull/790): Upgrade dependencies, including Hashicorp Raft to v1.3.0.

## v5.11.1 (April 13th 2021)
### Implementation changes and bug fixes
- [PR #783](https://github.com/rqlite/rqlite/pull/783): Create GZIP writer for every compression request. Fixes [issue #781](https://github.com/rqlite/rqlite/issues/781).

## v5.11.0 (April 12th 2021)
### New features
- [PR #776](https://github.com/rqlite/rqlite/pull/776), [PR #777](https://github.com/rqlite/rqlite/pull/777): Support specifying Dialer's local address when performing Join request. Fixes [issue #774](https://github.com/rqlite/rqlite/issues/774). Thanks @osxlinux

### Implementation changes and bug fixes
- [PR #782](https://github.com/rqlite/rqlite/pull/782): Better error messages for command unmarshaling.

## v5.10.2 (February 19th 2021)
### Implementation changes and bug fixes
- [PR #772](https://github.com/rqlite/rqlite/pull/772): Log launch command.

## v5.10.1 (February 8th 2021)
### Implementation changes and bug fixes
- [PR #769](https://github.com/rqlite/rqlite/pull/769): Upgrade to rqlite/go-sqlite3 v1.20.1, to address [a significant memory leak](https://www.philipotoole.com/plugging-a-memory-leak-in-rqlite/).

## v5.10.0 (February 7th 2021)
### New features
- [PR #742](https://github.com/rqlite/rqlite/pull/742): Add one-shot option to rqbench.
- [PR #745](https://github.com/rqlite/rqlite/pull/745): TLS version 1.0 and 1.1 disabled by default, but can be re-enabled at the command line. Fixes [issue #743](https://github.com/rqlite/rqlite/issues/743).

### Implementation changes and bug fixes
- [PR #738](https://github.com/rqlite/rqlite/pull/738): Don't use temp file when snapshotting database.
- [PR #739](https://github.com/rqlite/rqlite/pull/739): Don't use temp file when restoring an in-memory database.
- [PR #738](https://github.com/rqlite/rqlite/pull/738): Switch to rqlite fork of mattn/go-sqlite3. The SQLite C code remains unchanged.
- [PR #741](https://github.com/rqlite/rqlite/pull/741): Tighten up Store-level locking.
- [PR #747](https://github.com/rqlite/rqlite/pull/747): Time snapshot, restore, and startup times.
- [PR #750](https://github.com/rqlite/rqlite/pull/750): Build on-disk databases in-memory first. Fixes [issue #731](https://github.com/rqlite/rqlite/issues/731).
- [PR #754](https://github.com/rqlite/rqlite/pull/754): Support Noop commands in Raft Log.
- [PR #759](https://github.com/rqlite/rqlite/pull/759), [PR #760](https://github.com/rqlite/rqlite/pull/760): Close BoltDB on Store close.
- [PR #757](https://github.com/rqlite/rqlite/pull/757): More extensive system-level testing of Snapshot and Restore.
- [PR #762](https://github.com/rqlite/rqlite/pull/762): Convert Raft stats to numbers where possible. Fixes [issue #763](https://github.com/rqlite/rqlite/issues/763).
- [PR #764](https://github.com/rqlite/rqlite/pull/764): Add total Raft directory size to Store stats.
- [PR #764](https://github.com/rqlite/rqlite/pull/764): Close SQLite database only after Raft has been shut down.
- [PR #765](https://github.com/rqlite/rqlite/pull/765): Add auth-ok and auth-fail events to stats.

## v5.9.0 (January 24th 2021)
### New features
- [PR #734](https://github.com/rqlite/rqlite/pull/734): Better control over waiting for Leader at startup, via command line options.

### Implementation changes and bug fixes
- [PR #724](https://github.com/rqlite/rqlite/pull/724): rqlite CLI displays node version at startup.
- [PR #726](https://github.com/rqlite/rqlite/pull/726): Count number of legacy commands unmarshaled.
- [PR #733](https://github.com/rqlite/rqlite/pull/733): Clearer Raft log status during startup.
- [PR #735](https://github.com/rqlite/rqlite/pull/735): Implement policy over trailing Raft logs.

## v5.8.0 (December 28th 2020)

### New features
- [PR #716](https://github.com/rqlite/rqlite/pull/716): Support HTTP/2 protocol over TLS. Fixes [issue #516](https://github.com/rqlite/rqlite/issues/516).

### Implementation changes and bug fixes
- [PR #711](https://github.com/rqlite/rqlite/pull/711), [PR# 712](https://github.com/rqlite/rqlite/pull/712): Ignore join addresses if node already part of cluster. Fixes [issue #710](https://github.com/rqlite/rqlite/issues/710).
- [PR #715](https://github.com/rqlite/rqlite/pull/715): Compress SQLite database in Raft snapshot.
- [PR #717](https://github.com/rqlite/rqlite/pull/717): Add SQLite database page-centric size to status output.
- [PR #719](https://github.com/rqlite/rqlite/pull/719): Exit if any arguments passed at command line after data directory. Fixes [issue #718](https://github.com/rqlite/rqlite/issues/718).

## v5.7.0 (December 23rd 2020)

### New features
- [PR #696](https://github.com/rqlite/rqlite/pull/696): Benchmarking tool now supports query testing.

### Implementation changes and bug fixes
- [PR #694](https://github.com/rqlite/rqlite/pull/694): Display, in the CLI, the HTTP response body on HTTP status 503.
- [PR #703](https://github.com/rqlite/rqlite/pull/703): Fix potential panic during request parsing.
- [PR #705](https://github.com/rqlite/rqlite/pull/705): Use Protobuf for encoding Raft Log commands.

## v5.6.0 (November 17th 2020)

### New features
- [PR #692](https://github.com/rqlite/rqlite/pull/692): Support setting Raft leader lease timeout.

### Implementation changes and bug fixes
- [PR #693](https://github.com/rqlite/rqlite/pull/693): Upgrade Go mod dependencies, including upgrading Hashicorp Raft to v1.2.0.

## v5.5.1 (October 27th 2020)

- [PR #680](https://github.com/rqlite/rqlite/pull/680), [PR #681](https://github.com/rqlite/rqlite/pull/681): Add missing calls to set BasicAuth in CLI. Fixes [issue #678](https://github.com/rqlite/rqlite/issues/678).
- [PR #682](https://github.com/rqlite/rqlite/pull/682): Explicitly handle "no leader" during backup, and return redirect if necessary.
- [PR #683](https://github.com/rqlite/rqlite/pull/683): Restore request should re-read file every attempt.

## v5.5.0 (September 27th 2020)

### New features
- [PR #673](https://github.com/rqlite/rqlite/pull/673): Support parameterized statements. Fixes [issue #140](https://github.com/rqlite/rqlite/issues/140).

## v5.4.2 (September 25th 2020)

### Implementation changes and bug fixes
- [PR #672](https://github.com/rqlite/rqlite/pull/672): Fix issue causing HTTPS-only redirects.

## v5.4.1 (September 24th 2020)
_This release should not be used, due to a HTTP redirection bug._

### Implementation changes and bug fixes
- [PR #660](https://github.com/rqlite/rqlite/pull/660): Raft log size on disk now reported via status endpoint.
- [PR #670](https://github.com/rqlite/rqlite/pull/670): Add utilities for testing encrypted nodes.
- [PR #671](https://github.com/rqlite/rqlite/pull/671): Set Location for HTTP redirect properly for secure nodes.

## v5.4.0 (June 14th 2020)

### New features
- [PR #654](https://github.com/rqlite/rqlite/pull/654): Allow number of Join attempts and Join interval to be specified at startup. Fixes [issue #653](https://github.com/rqlite/rqlite/issues/653).

## v5.3.0 (May 13th 2020)

### New features
- [PR #641](https://github.com/rqlite/rqlite/pull/641): rqlite CLI now supports node removal.

## v5.2.0 (April 11th 2020)
This release fixes a very significant bug, whereby snapshotting was never occurring due to a zero snapshot-interval being passed to the Raft subsystem. This meant that the Raft log would grow without bound, and could result in very long start-up times if the Raft log was very large.

### New features
- [PR #637](https://github.com/rqlite/rqlite/pull/637): Allow the Raft snapshotting check interval to be set at launch time.

### Implementation changes and bug fixes
- [PR #637](https://github.com/rqlite/rqlite/pull/637): Set the Raft snapshot check interval to 30 seconds by default.

## v5.1.1 (March 28th 2020)
### Implementation changes and bug fixes
- [PR #636](https://github.com/rqlite/rqlite/pull/636): Check consistency level before freshness check. Thanks @wangfenjin

## v5.1.0 (January 10th 2020)

### New features
- [PR #613](https://github.com/rqlite/rqlite/pull/613): Support read-only, non-voting nodes. These provide read scalability for the system.
- [PR #614](https://github.com/rqlite/rqlite/pull/614): Support specifying minimum leader freshness with _None_ consistency queries.
- [PR #620](https://github.com/rqlite/rqlite/pull/620): Log level can be specified for Raft module.

## v5.0.0 (December 30th 2019)
This release uses a new Raft consensus version, with the move to Hashicorp Raft v1. As a result **the Raft system in 5.0 is not compatible with the 4.0 series**. To upgrade from an earlier version to this release you should backup your 4.0 leader node, and restore the database dump into a new 5.0 cluster.

The rqlite server also supports explicitly setting the node ID. While it's not required to set this, it's recommended for production clusters. See the [cluster documentation](https://github.com/rqlite/rqlite/blob/master/DOC/CLUSTER_MGMT.md) for more details.

The HTTP Query and Insert API remains unchanged in the 5.0 series relative to the 4.0 series.

### New features
- [PR #595](https://github.com/rqlite/rqlite/pull/595): rqlite CLI prints Welcome message on startup.
- [PR #608](https://github.com/rqlite/rqlite/pull/608): Add features list to status output.

### Implementation changes and bug fixes
- [PR #597](https://github.com/rqlite/rqlite/pull/597): Don't ignore any Join error, instead return it.
- [PR #598](https://github.com/rqlite/rqlite/pull/598): Ensure backup is correctly closed.
- [PR #600](https://github.com/rqlite/rqlite/pull/600): Move to Hashicorp Raft v1.1.1.
- [PR #601](https://github.com/rqlite/rqlite/pull/601): By default use Raft network address as node ID.
- [PR #602](https://github.com/rqlite/rqlite/pull/602): Add method to Store that returns leader ID.
- [PR #603](https://github.com/rqlite/rqlite/pull/603): Fix up status key name style.
- [PR #604](https://github.com/rqlite/rqlite/pull/604): JSON types are also text.
- [PR #605](https://github.com/rqlite/rqlite/pull/605): Broadcast Store meta via consensus.
- [PR #607](https://github.com/rqlite/rqlite/pull/607): Various Redirect fixes.
- [PR #609](https://github.com/rqlite/rqlite/pull/609): Simplify rqlite implementation.
- [PR #610](https://github.com/rqlite/rqlite/pull/610): Write node backup directly to HTTP response writer. Thanks @sum12.
- [PR #611](https://github.com/rqlite/rqlite/pull/611): Add variadic perm check functions to auth store.

## v4.6.0 (November 29th 2019)
_This release adds significant new functionality to the command-line tool, including much more control over backup and restore of the database. [Visit the Releases page](https://github.com/rqlite/rqlite/releases/tag/v4.6.0) to download this release._

### New features
- [PR #592](https://github.com/rqlite/rqlite/pull/592): Add _dump database_ command (to SQL text file) to CLI.
- [PR #585](https://github.com/rqlite/rqlite/pull/585): Add _backup_ command (to SQLite file) to CLI: Thanks @eariassoto.
- [PR #589](https://github.com/rqlite/rqlite/pull/589): Add _restore_ command (from SQLite file) to CLI. Thanks @eariassoto.
- [PR #584](https://github.com/rqlite/rqlite/pull/584): Support showing query timings in the CLI. Thanks @joaodrp.
- [PR #586](https://github.com/rqlite/rqlite/pull/586): rqlite CLI now supports command-recall via cursor key. Thanks @rhnvrm.
- [PR #564](https://github.com/rqlite/rqlite/pull/564): rqlite server supports specifying trusted root CA certificate. Thanks @zmedico.
- [PR #593](https://github.com/rqlite/rqlite/pull/593): rqlite CLI now supports [HTTP proxy (via Environment)](https://golang.org/pkg/net/http/#ProxyFromEnvironment). Thanks @paulstuart
- [PR #587](https://github.com/rqlite/rqlite/pull/587): Add [expvar](https://golang.org/pkg/expvar/) statistics to store.

### Implementation changes and bug fixes
- [PR #591](https://github.com/rqlite/rqlite/pull/591): Store layer supports generating SQL format backups.
- [PR #590](https://github.com/rqlite/rqlite/pull/590): DB layer supports generating SQL format backups.
- [PR #588](https://github.com/rqlite/rqlite/pull/588): Abort transaction if _load from backup_ operation fails.
- If joining a cluster via HTTP fails, try HTTPS. Fixes [issue #577](https://github.com/rqlite/rqlite/issues/577).

## v4.5.0 (April 24th 2019)
- [PR #551](https://github.com/rqlite/rqlite/pull/551): rqlite CLI supports specifying trusted root CA certificate. Thanks @zmedico.

## v4.4.0 (January 3rd 2019)
- Allow the Raft election timeout [to be set](https://github.com/rqlite/rqlite/commit/2e91858e1ee0feee19f4c20c6f56a21261bcd44a). 
 
## v4.3.1 (October 10th 2018)
- Allow a node to be re-added with same IP address and port, even though it was previously removed. Fixes [issue #534](https://github.com/rqlite/rqlite/issues/534).

## v4.3.0 (March 18th 2018)
- [PR #397](https://github.com/rqlite/rqlite/pull/397), [PR #399](https://github.com/rqlite/rqlite/pull/399): Support hashed passwords. Fixes [issue #395](https://github.com/rqlite/rqlite/issues/395). Thanks @sum12.

## v4.2.3 (February 21st 2018)
- [PR #389](https://github.com/rqlite/rqlite/pull/389): Log Store directory path on startup.
- [PR #392](https://github.com/rqlite/rqlite/pull/392): Return redirect if node removal attempted on follower. Fixes [issue #391](https://github.com/rqlite/rqlite/issues/391).

## v4.2.2 (December 7th 2017)
- [PR #383](https://github.com/rqlite/rqlite/pull/383): Fix unit tests after underlying SQLite master table changes.
- [PR #384](https://github.com/rqlite/rqlite/pull/384): "status" perm required to access Go runtime information.

## v4.2.1 (November 10th 2017)
- [PR #367](https://github.com/rqlite/rqlite/pull/367): Remove superfluous leading space at CLI prompt.
- [PR #368](https://github.com/rqlite/rqlite/pull/368): CLI displays clear error message when not authorized.
- [PR #370](https://github.com/rqlite/rqlite/pull/370): CLI does not need to indent JSON when making requests.
- [PR #373](https://github.com/rqlite/rqlite/pull/373), [PR #374](https://github.com/rqlite/rqlite/pull/374): Add simple INSERT-only benchmarking tool.

## v4.2.0 (October 19th 2017)
- [PR #354](https://github.com/rqlite/rqlite/pull/354): Vendor Raft.
- [PR #354](https://github.com/rqlite/rqlite/pull/354): Move to Go 1.9.1.

## v4.1.0 (September 3rd 2017)
- [PR #342](https://github.com/rqlite/rqlite/pull/342): Add missing Store parameters to diagnostic output.
- [PR #343](https://github.com/rqlite/rqlite/pull/343): Support fetching [expvar](https://golang.org/pkg/expvar/) information via CLI.
- [PR #344](https://github.com/rqlite/rqlite/pull/344): Make read-consistency query param value case-insensitive.
- [PR #345](https://github.com/rqlite/rqlite/pull/345): Add unit test coverage for status and expvar endpoints.

## v4.0.2 (August 8th 2017)
- [PR #337](https://github.com/rqlite/rqlite/pull/337): Include any query params with 301 redirect URL.

## v4.0.1 (August 4th 2017)
- [PR #316](https://github.com/rqlite/rqlite/pull/316): CLI doesn't need pretty nor timed responses from node.
- [PR #334](https://github.com/rqlite/rqlite/pull/334): Set Content-Type to "application/octet-stream" for backup endpoint. Fixes [issue #333](https://github.com/rqlite/rqlite/issues/333).

## v4.0.0 (June 18th 2017)
**The 4.0 release has renamed command-line options relative to earlier releases.** This means that previous commands used to launch rqlited will not work. However the command-line changes are cosmetic, and each previous option maps 1-to-1 to a renamed option. Otherwise deployments of earlier releases can be upgraded to the 4.0 series without any other work.

- [PR #309](https://github.com/rqlite/rqlite/pull/309): Tweak start-up logo.
- [PR #308](https://github.com/rqlite/rqlite/pull/308): Move to clearer command-line options.
- [PR #307](https://github.com/rqlite/rqlite/pull/307): Support node-to-node encryption. Fixes [issue #93](https://github.com/rqlite/rqlite/issues/93).
- [PR #310](https://github.com/rqlite/rqlite/pull/310): HTTP service supports registration of Status providers; Mux is first client.
- [PR #315](https://github.com/rqlite/rqlite/pull/315): Add status and help commands to CLI.

## v3.14.0 (May 4th 2017)
- [PR #304](https://github.com/rqlite/rqlite/pull/304): Switch to Go 1.8.1.

## v3.13.0 (April 3rd 2017)
- [PR #296](https://github.com/rqlite/rqlite/pull/296): Log Go version at startup.
- [PR #294](https://github.com/rqlite/rqlite/pull/294): Support multiple explicit join addresses.
- [PR #297](https://github.com/rqlite/rqlite/pull/297): CLI should explicitly handle redirects due to Go1.8. Fixes [issue #295](https://github.com/rqlite/rqlite/issues/295).

## v3.12.1 (March 2nd 2017)
- [PR #291](https://github.com/rqlite/rqlite/pull/291): Don't access Discovery Service if node already part of cluster.

## v3.12.0 (March 1st 2017)
- [PR #286](https://github.com/rqlite/rqlite/pull/286): Tweak help output.
- [PR #283](https://github.com/rqlite/rqlite/pull/283): Main code should log to stderr.
- [PR #280](https://github.com/rqlite/rqlite/pull/280), [PR #281](https://github.com/rqlite/rqlite/pull/281): Integrate with new Discovery Service.
- [PR #282](https://github.com/rqlite/rqlite/pull/282): Retry cluster-join attempts on failure.
- [PR #289](https://github.com/rqlite/rqlite/pull/289): rqlite HTTP clients should not automatically follow redirects.

## v3.11.0 (February 12th 2017)
- [PR #268](https://github.com/rqlite/rqlite/pull/268): Allow Store to wait for application of initial logs. Fixes [issue #260](https://github.com/rqlite/rqlite/issues/260).
- [PR #272](https://github.com/rqlite/rqlite/pull/272): Add commit, branch, GOOS, and GOARCH, to output of `--version`.
- [PR #274](https://github.com/rqlite/rqlite/pull/274): Use Hashicorp function to read peers. Thanks @WanliTian
- [PR #278](https://github.com/rqlite/rqlite/pull/278): Add support for dot-commands `.tables` and `.schema` to rqlite CLI. Fixes [issue #277](https://github.com/rqlite/rqlite/issues/277).

## v3.10.0 (January 29th 2017)
- [PR #261](https://github.com/rqlite/rqlite/pull/261): Allow Raft Apply timeout to be configurable.
- [PR #262](https://github.com/rqlite/rqlite/pull/262): Log GOOS and GOARCH at startup.

## v3.9.2 (January 14th 2017)
- [PR #253](https://github.com/rqlite/rqlite/pull/254): Handle nil row returned by SQL execer. Fixes [issue #253](https://github.com/rqlite/rqlite/issues/253).
- [PR #258](https://github.com/rqlite/rqlite/pull/258): Remove check that all queries begin with SELECT. Fixes [issue #255](https://github.com/rqlite/rqlite/issues/255).

## v3.9.1 (December 29th 2016)
- [PR #247](https://github.com/rqlite/rqlite/pull/247): Simplify loading of SQLite dump files via single command execution. Fixes [issue #246](https://github.com/rqlite/rqlite/issues/246).
- [PR #247](https://github.com/rqlite/rqlite/pull/247): Correct SQLite dump load authentication check.

## v3.9.0 (December 24th 2016)
- [PR #239](https://github.com/rqlite/rqlite/pull/239): Add an API to the `Store` layer for custom peers storage and logging. Thanks @tych0
- [PR #221](https://github.com/rqlite/rqlite/pull/221): Start full support for various SQLite text types. Fix [issue #240](https://github.com/rqlite/rqlite/issues/240).
- [PR #242](https://github.com/rqlite/rqlite/pull/242): Support direct copying of the database via the Store. Thanks @tych0.
- [PR #243](https://github.com/rqlite/rqlite/pull/243): Use Store logging everywhere in the Store package.

## v3.8.0 (December 15th 2016)
- [PR #230](https://github.com/rqlite/rqlite/pull/230): Move Chinook test data to idiomatic testdata directory.
- [PR #232](https://github.com/rqlite/rqlite/pull/232), [PR #233](https://github.com/rqlite/rqlite/pull/233): rqlite CLI now supports accessing secured rqlited nodes. Thanks @tych0.
- [PR #235](https://github.com/rqlite/rqlite/pull/235): Return correct error, if one occurs, during backup. Thanks @tych0.
- [PR #237](https://github.com/rqlite/rqlite/pull/237), [PR #238](https://github.com/rqlite/rqlite/pull/238): Support observing Raft changes. Thanks @tych0

## v3.7.0 (November 24th 2016)
- With this release rqlite is moving to Go 1.7.
- [PR #206](https://github.com/rqlite/rqlite/pull/206), [#217](https://github.com/rqlite/rqlite/pull/217): Support loading data directly from SQLite dump files.
- [PR #209](https://github.com/rqlite/rqlite/pull/209): Tweak help output.
- [PR #229](https://github.com/rqlite/rqlite/pull/229): Remove explicit control of foreign key constraints.
- [PR #207](https://github.com/rqlite/rqlite/pull/207): Database supports returning foreign key constraint status.
- [PR #211](https://github.com/rqlite/rqlite/pull/211): Diagnostics show actual foreign key constraint state.
- [PR #212](https://github.com/rqlite/rqlite/pull/212): Add database configuration to diagnostics output.
- [PR #224](https://github.com/rqlite/rqlite/pull/224), [PR #225](https://github.com/rqlite/rqlite/pull/225): Add low-level database layer expvar stats.

## v3.6.0 (October 1st 2016)
- [PR #195](https://github.com/rqlite/rqlite/pull/195): Set Content-type "application/json" on all HTTP responses.
- [PR #193](https://github.com/rqlite/rqlite/pull/193): Allow joining a cluster through any node, not just the leader.
- [PR #187](https://github.com/rqlite/rqlite/pull/187): Support memory profiling.
- Go cyclo complexity changes.
- With this release Windows compatibility is checked with every build.

## v3.5.0 (September 5th 2016)
- [PR #185](https://github.com/rqlite/rqlite/pull/185): Enable foreign key constraints by default.

## v3.4.1 (September 1st 2016)
- [PR #175](https://github.com/rqlite/rqlite/pull/175): Simplify error handling of Update Peers API.
- [PR #170](https://github.com/rqlite/rqlite/pull/170): Log any failure to call `Serve()` on HTTP service.
- Go lint fixes.
- Go cyclo complexity changes.

## v3.4.0 (July 7th 2016)
- [PR #159](https://github.com/rqlite/rqlite/pull/159): All HTTP responses set X-RQLITE-VERSION.

## v3.3.0 (June 1st 2016)
- [PR #151](https://github.com/rqlite/rqlite/pull/151): Support configurable Raft heartbeat timeout.
- [PR #149](https://github.com/rqlite/rqlite/pull/149): Support configurable Raft snapshot thresholds.
- [PR #148](https://github.com/rqlite/rqlite/pull/148): Support pprof information over HTTP.
- [PR #154](https://github.com/rqlite/rqlite/pull/154): CLI now redirects to leader if necessary.
- [PR #155](https://github.com/rqlite/rqlite/pull/155): CLI now handles "no rows" correctly.

## v3.2.1 (May 22nd 2016)
- [PR #143](https://github.com/rqlite/rqlite/pull/143): Use DELETE as HTTP method to remove nodes.

## v3.2.0 (May 21st 2016)
- [PR #142](https://github.com/rqlite/rqlite/pull/142): Use correct HTTP methods on all endpoints.
- [PR #137](https://github.com/rqlite/rqlite/pull/137): Use resolved version of joining node's address.
- [PR #136](https://github.com/rqlite/rqlite/pull/136): Better errors on join failures.
- [PR #133](https://github.com/rqlite/rqlite/pull/133): Add Peers to status output.
- [PR #132](https://github.com/rqlite/rqlite/pull/132): Support removing a node from a cluster.
- [PR #131](https://github.com/rqlite/rqlite/pull/131): Only convert []byte from database to string if "text". Thanks @bkeroackdsc
- [PR #129](https://github.com/rqlite/rqlite/pull/129): Verify all statements sent to query endpoint begin with "SELECT".
- [PR #141](https://github.com/rqlite/rqlite/pull/141): Store methods to expose node Raft state. Thanks @bkeroack

## v3.1.0 (May 4th 2016)
- [PR #118](https://github.com/rqlite/rqlite/pull/118): New rqlite CLI. Thanks @mkideal
- [PR #125](https://github.com/rqlite/rqlite/pull/125): Add Go runtime details to status endpoint.

## v3.0.1 (May 1st 2016)
- [PR #117](https://github.com/rqlite/rqlite/pull/117): Use Raft advertise address, if exists, during join.

## v3.0.0 (May 1st 2016)
**The Raft log format in 3.0 is not compatible with the 2.0 series**. To upgrade from an earlier version to this release you should backup your 2.0 leader node, and replay the database dump into a new 3.0 cluster. The HTTP API remains unchanged however.

- [PR #116](https://github.com/rqlite/rqlite/pull/116): Allow HTTP advertise address to be set.
- [PR #115](https://github.com/rqlite/rqlite/pull/115): Support advertising address different than Raft bind address.
- [PR #113](https://github.com/rqlite/rqlite/pull/113): Switch to in-memory SQLite databases by default.
- [PR #109](https://github.com/rqlite/rqlite/pull/109): Nodes broadcast meta to cluster via Raft.
- [PR #109](https://github.com/rqlite/rqlite/pull/109), [PR #111](https://github.com/rqlite/rqlite/pull/111): Leader redirection
- [PR #104](https://github.com/rqlite/rqlite/pull/104): Handle the `-join` option sensibly when already member of cluster.

## v2.2.2 (April 24th 2016)
- [PR #96](https://github.com/rqlite/rqlite/pull/96): Add build time to status output.
- [PR #101](https://github.com/rqlite/rqlite/pull/101): Fix restore to in-memory databases.

## v2.2.1 (April 19th 2016)
- [PR #95](https://github.com/rqlite/rqlite/pull/95): Correctly set HTTP authentication.

## v2.2.0 (April 18th 2016)
- [PR #84](https://github.com/rqlite/rqlite/pull/84): Encrypted API (HTTPS) now supported.
- [PR #85](https://github.com/rqlite/rqlite/pull/85): BasicAuth support.
- [PR #85](https://github.com/rqlite/rqlite/pull/85): User-level permissions support.
- Print rqlited logo on start-up.
- End-to-end single-node and multi-node unit tests.

## 2.1 (April 9th 2016)
- [PR #76](https://github.com/rqlite/rqlite/pull/76): Obey timing information display at database level.
- [PR #77](https://github.com/rqlite/rqlite/pull/77): Add version information to binary.

## 2.0 (April 5th 2016)
- `timings` URL param to control presence of timing information in response.
- [PR #74](https://github.com/rqlite/rqlite/pull/74): Use SQLite connection directly. Thanks @zmedico.
- Update operations return last-inserted ID.
- Column-oriented API responses.
- Types in API response body.
- Query times in addition to sum of query times.
- New Raft consensus module, built on Hashicorp's implementation.
- Hot backup support.
- Selectable read-consistency levels of none, weak, and strong.
- SQLite file size added to HTTP API status endpoint.
- expvar support added to HTTP server.

## 1.0 (June 23rd 2015)
_This version is a retagged version of code moved from a personal repository. The original code was first tagged in mid-2015._

Check out [this tag](https://github.com/rqlite/rqlite/releases/tag/v1.0) for full details.

