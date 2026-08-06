# Container run times
- Defualt was containerd, but other came out to limit dependancy

# Container networking interface
- As long as your container follows the standard, you can itneract with kubernetes
- + can write your own drivers, following CSI standard ( Universal )

- Defines a set of RPCs, that must be defined by the driver.
    - I.e:
        - Create Volume
        - Del vol
        - Controller push volume
