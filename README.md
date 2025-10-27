# kubevirt-ip-helper-webhook

The kubevirt-ip-helper-webhook is a webhook service for the kubevirt-ip-helper which prevents deleting IPPools which are in use.

## Prerequisites

The following components need to be installed/configured to use the kubevirt-ip-helper-webhook:

* kubevirt-ip-helper

## Building the container

There is a Dockerfile in the current directory which can be used to build the container, for example:

```SH
[docker|podman] build -t <DOCKER_REGISTRY_URI>/kubevirt-ip-helper-webhook:latest .
```

Then push it to the remote container registry target, for example:

```SH
[docker|podman] push <DOCKER_REGISTRY_URI>/kubevirt-ip-helper-webhook:latest
```

## Deploying the container

Use the deployment.yaml template which is located in the templates directory, for example:

```SH
kubectl create -f deployments/deployment.yaml
```

### Logging

By default only the startup, error and warning logs are enabled. More logging can be enabled by changing the LOGLEVEL environment setting in the kubevirt-ip-helper-webhook deployment. The supported loglevels are INFO, DEBUG and TRACE.

# License

Copyright (c) 2025 Joey Loman <joey@binbash.org>

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.