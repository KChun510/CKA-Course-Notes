# What if we need our own scheduling algo?
- Specific for our purpose. 

## Using mult schedulers in parralel. 
- You can define which shceduler to use in the a resource.
- Using `kind: KubeSchedulerConfiguration`
- Pointing it to a custom config file.
    - In the pod example, you set the config path, in spec: command: --config section. 

## Schedulers within a deployment.
- Look at docs lol


