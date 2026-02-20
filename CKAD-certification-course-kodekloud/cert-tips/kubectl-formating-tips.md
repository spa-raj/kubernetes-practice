#### The default output format for all kubectl commands is the human-readable plain-text format.

#### The `-o` flag allows us to output the details in several different formats.

**kubectl [command] [TYPE] [NAME] -o**

#### Here are some of the commonly used formats:

##### `-o json`: Output a JSON formatted API object.
##### `-o name`: Print only the resource name and nothing else.
##### `-o wide`: Output in the plain-text format with any additional information.
##### `-o yaml`: Output a YAML formatted API object.

#### Here are some useful examples:
##### 1. Output with JSON format:
```bash
kubectl create namespace test-123 --dry-run -o json
```
```json
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "test-123",
        "creationTimestamp": null
    },
    "spec": {},
    "status": {}
}
```
##### 2. Output with YAML format:
```bash
kubectl create namespace test-123 --dry-run -o yaml
```
```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: test-123
spec: {}
status: {}
```
##### 3. Output with wide (additional details):
```bash
kubectl get pods -o wide
```
```
NAME      READY   STATUS    RESTARTS   AGE     IP          NODE     NOMINATED NODE   READINESS GATES
busybox   1/1     Running   0          3m39s   10.36.0.2   node01          <none>         <none>
ningx     1/1     Running   0          7m32s   10.44.0.1   node03          <none>         <none>
redis     1/1     Running   0          3m59s   10.36.0.1   node01          <none>         <none> 
```

#### For more details, refer:

##### 1. https://kubernetes.io/docs/reference/kubectl/overview/
##### 2. https://kubernetes.io/docs/reference/kubectl/cheatsheet/