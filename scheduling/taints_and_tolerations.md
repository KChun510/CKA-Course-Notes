# Anology ( Bug and person )
- TO prevent bug, we spray repleant. 
- The bug is intolerant to the smell.
    - There could be other bugs that dont mind the taint on the person


- Person = Node
- Pods = Bug

## Set restrictions on what pods can be set on a node
- With no resitrictions, kubernetes splits pods across all nodes.

- Can, set a `taint` on a node.
- Can, set a `toleration` on a node.
    - By default, no pods can `tolerate` a `taint` given on a node.

- I.e: We want to set pod D on node 1.
    - Set a taint on `node 1`, example: taint -> blue
    - Set a toleration on `pod D`, example: toleration -> blue

That slide has the right structure, but the ending should be called the **effect**, not `taint-effect`.

````md
# Taint Command Format

```bash
kubectl taint nodes <node-name> <key>=<value>:<effect>
````

Example:

```bash
kubectl taint nodes node01 app=blue:NoSchedule
```

Meaning:

```md
Node `node01` now has a taint:

key: app
value: blue
effect: NoSchedule
```

---

# Effects

```bash
NoSchedule
```

Do not schedule new pods here unless they tolerate the taint.

```bash
PreferNoSchedule
```

Try not to schedule pods here, but it is not strict.

```bash
NoExecute
```

Do not schedule new pods here, and evict existing pods that do not tolerate the taint.

---

# Remove Taint

```bash
kubectl taint nodes node01 app=blue:NoSchedule-
```

The `-` at the end removes the taint.

````bash
For the screenshot command, read it as:

kubectl taint nodes node-name key=value:effect
````

Not literally `taint-effect`.

