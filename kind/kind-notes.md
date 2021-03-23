### kind-tutorial


```bash
brew install kind
```

Create `kind-multi-node.yml` config file based on this:

[Origin](https://kind.sigs.k8s.io/docs/user/configuration/#nodes)

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
# One control plane node and three "workers".
#
# While these will not add more real compute capacity and
# have limited isolation, this can be useful for testing
# rolling updates etc.
#
# The API-server and other control plane components will be
# on the control-plane node.
#
# You probably don't need this unless you are testing Kubernetes itself.
nodes:
- role: control-plane
- role: worker
- role: worker
- role: worker
```


```bash
kind create cluster --config kind-multi-node.yml
```
