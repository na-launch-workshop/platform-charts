# Red Hat Launch Workshop - Charts

![Stable Release Charts](https://github.com/na-launch-workshop/platform-charts/actions/workflows/stable-release-charts.yaml/badge.svg)
![pages-build-deployment](https://github.com/na-launch-workshop/platform-charts/actions/workflows/pages/pages-build-deployment/badge.svg)

## Chart Repositories

The following are the Helm chart repositories for the workshop:

* platform-charts (this repository) - Helm chart and operator deployments of various tools
* [platform-supporting-charts](https://github.com/na-launch-workshop/platform-supporting-charts) - Helm charts containing custom integration code

## Updating Helm Charts

To update Helm charts in this repository, follow these instructions:
  
1. Fork this repository
2. Update the content in the relevant chart(s), and **bump the chart version**.
3. Update the `orchestrator` and `rollout-controller` charts which call the dependent charts, and **bump the chart version** as well.
4. Push to main branch (or open a pull request, and the maintainers will accept and merge) which will kick off a [chart build job](https://github.com/na-launch-workshop/platform-charts/blob/main/.github/workflows/stable-release-charts.yaml).  Verify the chart [builds successfully](https://github.com/na-launch-workshop/platform-charts/actions).
5. In your deployed ArgoCD, go to the `infrastructure-orchestrator` application and press Refresh + Sync, and then to `infrastructure-rollout-controller` application and press Refresh + Sync.

