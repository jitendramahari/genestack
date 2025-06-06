# Deploy a Memcached

## Deploy the Memcached Cluster

!!! example "Run the memcached deployment Script `/opt/genestack/bin/install-memcached.sh` You can include paramaters to deploy aio or base-monitoring. No paramaters deploys base"

    ``` shell
    --8<-- "bin/install-memcached.sh"
    ```

!!! note

    Memcached has a base configuration which is HA and production ready. If you're deploying on a small cluster the `aio` configuration may better suit the needs of the environment.

### Alternative - Deploy the Memcached Cluster With Monitoring Enabled

View the [memcached exporter](prometheus-memcached-exporter.md) instructions to install a HA ready memcached cluster with monitoring and metric collection enabled.

## Verify readiness with the following command

``` shell
kubectl --namespace openstack get horizontalpodautoscaler.autoscaling memcached -w
```

!!! Genestack

    For more information on how to enable memcached monitoring with prometheus, see the [memcached exporter](prometheus-monitoring-overview.md) documentation.
