## A small note about URI and URL

A URL is a resource locator, which tells how to find the resource.
A URI on the other hand describes what a resource is.


if we say /192.168.1.10/users/john, it is an URI because it indicates that john is a user resource on the network
it can become a URL when we prepend a `http:/`, because it tells how to reach that resource(use http protocol)

Cloudera Manager is the standard deployment and monitoring software used by admins working with CDH(Cloudera Distribution of Apache Hadoop)
Cloudera recommends to use Cloudera Manager for the deployment of its products. The cloudera manager provides an REST API interface called CM API with wich administrators can manage the resources in Cloudera Manager


The CM server defines a set of resources at its core
Resources of CM
* Cluster
* Service
* Service Role
* Service Role Config
* Host
* User

And the CM API provide access to these resources, so that we can create, update, view and delete these resources

uris of resources

cluster - cm_ip:port/api/version/clusters/cluster_name
service - cm_ip:port/api/version/clusters/cluster_name/services/service_name
service role - cm_ip:port/api/version/clusters/cluster_name/services/service_name/roles/role_name
hosts - cm_ip:port/api/version/cm/hosts/host
user - cm_ip:port/api/version/cm/users/user

- Create - PUT
- Update - POST
- View - GET
- Delete - DELETE

By combining these two tables we can look at how to create a cluster

### Creating a cluster:
  ```
  curl -X PUT -u 'username:password' 'http://cm_host:cm_port/api/{api_version}/clusters/{cluster_name}'
  ```

do a POST operation
The top level resource in CM is the clusters. Multiple clusters can be created and managed by Cloudera Manager
