# Workloads
- Want to ensure pri workloads, get ran before lower pri workloads. 
- Configurable to any namespace, but specify pri of target pods.

## Setting prioitys:
- Numerical value: ["-2,147,483,648", "2,000,000,000"]

# What if high prob comes in but no more resource/ space.
- Options:
    - `preemptionPolicy: never | PreemptLowerPri... `
        - Never: Waits for other jobs to finish.
        - PreemptLower..: Kills lower pri jobs.
