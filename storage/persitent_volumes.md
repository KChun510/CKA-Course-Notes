# large env, alot of pods
- Hard to manually confifure a external volume binding for each new resource.

## Solution:
- A cluster wide, set of perstitent volumes.
    - Defing a `pool` of volumes.
    - That can be used via `claims`
