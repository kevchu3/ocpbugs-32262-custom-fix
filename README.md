# Custom fix script for OCPBUGS-32262

## Background

After cluster is upgraded from 4.14.y to 4.15.z, when the operator approval plan is set to manual, the operator fails at operator installing (upgrading) if you want to install new version bundle.  More information about this bug is described in the following links:
* [OCPBUGS-32262](https://issues.redhat.com/browse/OCPBUGS-32262)
* Red Hat Knowledgebase solution [https://access.redhat.com/solutions/7112405](https://access.redhat.com/solutions/7112405)
* Red Hat Knowledgebase solution [https://access.redhat.com/solutions/7105251](https://access.redhat.com/solutions/7105251)

## Setup

NOTE: As a customization of this fix, I skipped recovery steps for the OpenShift Virtualization operator only.  Feel free to remove this customization so that this fix will apply to all operators.

This custom fix is intended to automate the resolution of this bug as described in the Red Hat Knowledgebase solutions, so that it can be deployed via GitOps.

To apply this fix, create the `ocpbugs-32262-fix` namespace, job, and related manifests:
```
oc new-project ocpbugs-32262-fix
oc apply -f manifests
```
