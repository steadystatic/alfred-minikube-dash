# alfred-minikube-dash

Alfred.app keyword trigger workflow that opens current Minikube Kubernetes Dashboard in your default browser

## How to use:

Mac only - requires [Alfred.app](https://www.alfredapp.com) and Python (which should already be on your system anyway). 

This works with any URL but for this example I'm using [Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/). When you start your Minikube session pass the `--url` flag and redirect the url to a temp file:

```
minikube dashboard --url >| /tmp/kubedash
```

Install the workflow binary in Alfred and enable it.

Now whenever you need to check your dashboard invoke Alfred and type keyword 'minidash' the URL will open in your default system browser (via this command: `python -m webbrowser -t "$(tail -n 1 /tmp/kubedash)"`)


