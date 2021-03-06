# alfred-minikube-dash

Alfred.app keyword trigger workflow that opens current Minikube Kubernetes Dashboard in your default browser

## How to use:

Mac only - requires [Alfred.app](https://www.alfredapp.com) and Python (which should already be on your system anyway). 

This works with any URL but for this example I'm using [Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/). When you start your Minikube session pass the `--url` flag and redirect the url to a temp file:

```
minikube dashboard --url >| /tmp/kubedash
```

Download, install, and enable the workflow binary in this repo: [OpenMinikubeDashboardURL.alfredworkflow](https://github.com/steadystatic/alfred-minikube-dash/blob/master/OpenMinikubeDashboardURL.alfredworkflow?raw=true)

Now whenever you need to check your dashboard invoke Alfred and type keyword 'minidash' the URL will open in your default system browser (via this command: `python -m webbrowser -t "$(tail -n 1 /tmp/kubedash)"`)

Also included in the binary are two simple bash keyword snippet expansions:

- `mkip` copies/pastes current Minikube machine's IP address from clipboard (provided current Kubernetes context is 'minikube'...check via `kubectl config current-context`)
- `mkdash` pastes the current URL of the Minikube dashboard (without opening browser)


