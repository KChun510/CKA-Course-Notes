# In place resizing
- When you change a pod/ change resourceson a pod. 
    - `Pod replacement workflow`:
        - Destory pod
        - And deploy new pod with new update
        - !Can raise issues with statful applications!

## Beta feature (In-place Pod Resizing)
- Need to enable the option, as a `feature gate`
- Essetially: You can define what changesto the pod def, will kickoff the replament workflow

## Limitations:
- only cpu and mem resources
- QoS cannot change
- etc. 
