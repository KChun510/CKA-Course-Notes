# Cluster Arch

- Anology of ships, host your appliaction in form of containers.
- Load containers onto a ship, and direct the ship.

## Two kinds of ships
1) Cargo Ships
    - Each node is a ship/ *worker nodes*, can load containers.
    - Host application of containers
2) Control Ships
    - Controls how to load the containers onto the worker nodes.
    - Relate to the *Master Node*
    - Manage, plan, schedule, Monitor nodes

### Control pane comps
- Need to maintain info about worker nodes/ ships. 

#### What holds information on current ships? **etcd cluster**
- All meta data stored in **etcd**, a Key Val db holding meta data of ships

#### When ships arrive, **Crains/ KUBE-scheduler**
- You load containers on them, using crains.
- Crains identifies the right ship, dest, type of continaers, all metadate.
- This is the **Kube-Scheduler**

#### Controller manager

##### Node-Controller
- Resposnible for onbording new nodes

##### Replication-Controller
- Ensures desired # of containers are running.

## How does each comp in this control pane, communitcate with each other??

### **Kube-apiserver**, is the primary management comp.
- respsobile for orchastrating all operations within the cluster

## Runtime engines:
- everthing needs to be ran in a container. The master node, can all be hosted i whitin their own containers. 
    - We know docker, but there are others container d, rocket, etc

## Cargo ships/ Captains (a.k.a **kubelet** )
- The captain is resposible for communcation with the master ship.
    - Sending continual reports to the captain. 
- Listens to instructions from the *Kubeapiserver*. 

## Challange, inter Node communcication. (a.k.a **kubeproxyservice**)
- For example, a Web Server can be running on a node, while a db is running on a different node. How do they talk to each other? Use a PROXY!

# Final self summary:
- There are two kinds of nodes.
1) Worker nodes
2) Master nodes

## Worker nodes
- Hold a collection of containers.
- With a captain/ *kubelet*, listening to commands sent from our master node/ mother ship. 
- Communicate with each other via the *kube-proxy*

## Master nodes
- Act as the control pane/ orchrastrator of worker nodes.

### Master nodes comps

- **etcd** cluster:
    - A key value db, that holds metadata i.e: node health about deployed nodes

- **controller-manager**:
    - Node controller, responsible for onboardin of new nodes
    - Repliaction controller, ensures # of nodes are running

- **kube-scheduler**:
    - Has access to the meta data of all nodes + is used to load containers into worker nodes.

- **kube-apiserver**:
    - The commication link between all of these master comps.






