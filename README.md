S2I Repository to Build OpenShift Origin
========================================

Build the OpenShift client (`oc`) for different platforms using an OpenShift cluster

To use this builder, instantiate the `origin-builder` template with new-app, preferably in its own namespace.

To build origin master, no parameters are needed, default client platform is Mac (darwin/amd64):

```bash
oc new-app -f https://raw.githubusercontent.com/csrwng/build-origin/master/origin-builder.yaml
```

To build a binary for Windows or Linux, specify the `PLATFORM` parameter. Valid values are
`darwin/amd64`, `windows/amd64`, `linux/amd64`

```bash
oc new-app -f https://raw.githubusercontent.com/csrwng/build-origin/master/origin-builder.yaml \
   -p PLATFORM=windows/amd64
```

To build the code from a Github pull request, specify the `PR` parameter:

```bash
oc new-app -f https://raw.githubusercontent.com/csrwng/build-origin/master/origin-builder.yaml \
   -p PR=13112
```

To build an alternate fork or branch, specify a SOURCE_URL and SOURCE_REF (default SOURCE_REF is `master`):

```bash
oc new-app -f https://raw.githubusercontent.com/csrwng/build-origin/master/origin-builder.yaml \
   -p SOURCE_URL=https://github.com/csrwng/origin.git \
   -p SOURCE_REF=my_branch
```
