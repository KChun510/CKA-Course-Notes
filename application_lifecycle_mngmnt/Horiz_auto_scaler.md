# Horizontal Pod Autoscaler
- Continuously monitors pod metrics using `top` command.
- Using that data, it dynamically deploys new pods

- Autoscaler, first reads `request` and `limits`, in pod def file as thresholds. If a pod reaches 50% of the threshold will spawn a new pod. 


