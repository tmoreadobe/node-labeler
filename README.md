# Node labeler
This is a very small tool that can run as a DaemonSet inside your
Kubernetes cluster which will automatically label your nodes based
on the product and vendor.  This can help with things like running
specific monitoring tools on specific hardware.

This is an example of labeled Dell PowerEdge machine:

    Labels:             beta.kubernetes.io/arch=amd64
                        beta.kubernetes.io/os=linux
                        kubernetes.io/arch=amd64
                        kubernetes.io/hostname=<snip>
                        kubernetes.io/os=linux
                        node-role.kubernetes.io/master=
                        node.vexxhost.com/product=poweredge-r640
                        node.vexxhost.com/vendor=dell-inc

In addition, we provide a very simple manifest attached inside this
repository which helps you setup a service account that is locked
down to only `GET` and `PATCH` nodes in the Kubernetes API with the
code for a DaemonSet.   It shouldn't require any changes to get going
on your cluster.