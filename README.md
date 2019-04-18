# alfred-minikube-dash

Alfred.app keyword trigger workflow that opens current Minikube Kubernetes Dashboard in your default browser

## How to use:

Mac only - requires Alfred.app and this works with any URL but try aliasing this and using when you start your Minikube session:

```
minikube dashboard --url >| /tmp/kubedash
```

Install the workflow binary in Alfred and enable it.

Now when you need to check your dashboard invoke Alfred and type keyword 'minidash'
