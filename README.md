# reproducer-03544800

```
oc apply -k https://github.com/gmeghnag/reproducer-03544800.git
oc logs -n rh-case-03544800 $(oc get po -l app=builds-pods-storage-collector -n rh-case-03544800 -o jsonpath='{.items[0].metadata.name}') -f | jq
```

## Expected output
```
{
  "DateTimeUTC": "2023-07-25T12:16:59Z",
  "Node": "ip-10-0-129-153.eu-central-1.compute.internal",
  "Namespace": "default",
  "PodName": "reproducer-03544800-1-build",
  "UsedGB": "20.018962860107422"
}
{
  "DateTimeUTC": "2023-07-25T12:17:20Z",
  "Node": "ip-10-0-129-153.eu-central-1.compute.internal",
  "Namespace": "default",
  "PodName": "reproducer-03544800-1-build",
  "UsedGB": "20.018962860107422"
}
..
```

## How to test
```
curl -sk https://raw.githubusercontent.com/gmeghnag/reproducer-03544800/main/Dockerfile | oc new-build -n default --to=reproducer-03544800 -D  -
```

