# Integrate OCP4 compliance operator with ACS

## Info

Refer to https://redhat-scholars.github.io/acs-workshop/acs-workshop/08-compliance.html for detailed explanation.


## Set up

```bash
cd operator
oc apply -k .
```

Wait for compliance operator CSV installed successfully:

```bash
watch oc get csv
```

```bash
NAME                          DISPLAY               VERSION   REPLACES   PHASE
compliance-operator.v0.1.48   Compliance Operator   0.1.48               Succeeded
```

Then create ScanSettingBinding

```bash
cd ..
cd scansettings
oc apply -k .
```

```bash
oc get scansettingbinding cis-scan -n openshift-compliance -o yaml
```

```bash
watch oc get compliancescan -n openshift-compliance ocp4-cis
```
