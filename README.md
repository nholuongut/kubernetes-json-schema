# Kubernetes JSON Schemas

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## Fork

This is a fork from [nholuongut/kubernetes-json-schema](https://github.com/nholuongut/kubernetes-json-schema)
with updated scripts for easier maintenance, as well as schemas for all recent
Kubernetes versions.

This repository is kept up-to-date automatically every day using Github Actions.


## Usage

### Kubeconform

This is the default schema repository used by [Kubeconform](https://github.com/nholuongut/kubeconform), and does not
need to be specified. When using multiple schema repositories, this repo can be referred to using the alias *default*.

```
# All 3 are equivalent
$ kubeconform deployment.yaml
$ kubeconform -schema-location default deployment.yaml
$ kubeconform -schema-location 'https://raw.githubusercontent.com/yannh/kubernetes-json-schema/master/{{ .NormalizedKubernetesVersion }}-standalone{{ .StrictSuffix }}/{{ .ResourceKind }}{{ .KindSuffix }}.json' deployment.yaml
Summary: 1 resource found in 1 file - Valid: 1, Invalid: 0, Errors: 0, Skipped: 0
```

### Kubeval

```
$ kubeval --strict --schema-location https://raw.githubusercontent.com/yannh/kubernetes-json-schema/master/ deployment.yaml
PASS - deployment.yaml contains a valid Deployment
```

To run `kubeval` against a specific Kubernetes version, pass the `-v` argument
```sh
$ kubeval -v 1.19.8 -s  https://raw.githubusercontent.com/yannh/kubernetes-json-schema/master ingress.yaml
PASS - ingress.yaml contains a valid Ingress (ingress)
```

## Building the schemas yourself

The tooling for generating these schemas is [a fork](https://github.com/nholuongut/openapi2jsonschema)
from the original [openapi2jsonschema](https://github.com/nholuongut/openapi2jsonschema). See *build.sh*.

It's not Kubernetes specific and should work with other OpenAPI
APIs too. This should be useful if you're using a pre-release or otherwise
modified version of Kubernetes, or something like OpenShift which extends the
standard APIs with additional types.

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: Nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)
* [PayPal.me](https://www.paypal.com/paypalme/nholuongut)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟