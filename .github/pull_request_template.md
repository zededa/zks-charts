## Issue: <!-- link the issue or issues this PR resolves here -->
<!-- If your PR depends on changes from another pr link them here and describe why they are needed in your solution section. -->

#### Pull Requests Rules

- `Never remove an already released chart!`
- Each Pull Request should only modify one chart with its dependencies.


Please create your Pull Request title following this rule:

```
[dev-v2.X] <chart> <version> <action>
[release-v2.X] <chart> <version> <action>
```

- `<chart>`: The full name of the charts exactly how it is written under `/charts folder`
- `<version>`: The full version of the chart, exactly how it is written under `release.yaml`
- `<action>`: `update`; `remove`; `add`

##### release.yaml
- Each chart version in release.yaml DOES NOT modify an already released chart. If so, stop and modify the versions so that it releases a net-new chart.
- Each chart version in release.yaml IS exactly 1 more patch or minor version than the last released chart version. If not, stop and modify the versions so that it releases a net-new chart.

##### Chart.yaml and index.yaml
- The `index.yaml` file has an entry for your new chart version.
- The `index.yaml` entries for each chart matches the `Chart.yaml` for each chart.
- Each chart has ALL required annotations
  - kube-version annotation
  - rancher-version annotation
  - permits-os annotation (indicates Windows and/or Linux)