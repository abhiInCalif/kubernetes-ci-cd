# kubernetes-ci-cd
A CI CD project for K8s that allows you to spawn a new cluster for each test.

## Use Case
App developers need a way to test their changes in a holistic way. Infrastructure engineers need a way to run their tests in an actual cluster, but running these clusters locally is memory intensive and not ideal for tracking purposes. This tool should allow app developers and infrastructure engineers to be able to launch a new cluster per commit, and have their entire stack loaded into a k8s cluster to run e2e tests against.

## Requirements
1. Should be a command line cli
2. Should have a `run-tests` option
3. Upon running the `run-test` option, the cli should launch a Kubernetes cluster on either GKE, EKS, or AKS.
4. Upon initializing the cluster, the cli should install all your service files onto the cluster.
5. Upon installing the service manifests, the cli should install all dependent helm charts.
6. Once everything has been installed (and all recent version upgrades have been made), the cli should run the pre-defined set of e2e tests (located in some folder that can be configured) as a job in the k8s cluster.
7. The results of each test (or job) should be tabulated via logs, and collected for later display to the user.
8. The user should, after all the jobs have run, be able to see the output from the tests and see which ones passed and which ones did not.
9. After all the tests are done running, the `cli` should delete the K8s cluster, so that you don't have to pay for it while no tests are being run.

## Implementation Details
TBD.
