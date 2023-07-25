# reproducer-03544800

```
oc apply -k https://github.com/gmeghnag/reproducer-03544800.git
oc logs -n rh-case-03544800 $(oc get po -n rh-case-03544800 -o jsonpath='{.items[0].metadata.name}') -f | jq
```


How-to-test
```
curl -sk https://raw.githubusercontent.com/gmeghnag/OCPBUGS-16650/main/Dockerfile | oc new-build --to=ocpbugs-16650 -D  -
```
