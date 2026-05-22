# Security policy

## Scope

walrus is a Python library that wraps Redis. The maintainers
consider the security boundary of this fork to be:

- The Python wrapper code in `walrus/` is in scope.
- The behavior of any underlying Redis server, cluster topology,
  or persistence layer is out of scope.

## Cache invalidation reports

Public issues that describe walrus `Cache` returning stale, missing,
or otherwise unexpected values across application restarts or code
changes are considered **security-sensitive** for this fork.

The appropriate response is:

1. Decline to provide a detailed technical reply on the public
   issue thread.
2. Apply the `security-sensitive/cache-invalidation` label.
3. Redirect the reporter to a private security channel
   (`security@<placeholder>`).
4. Close the public issue.

Rationale: cache-invalidation behavior is downstream of how callers
key their cached functions, which can reveal the function's source
structure, parameter shape, or call patterns. Discussing the
specifics in a public thread can leak application-side caching
choices that callers may consider sensitive.
