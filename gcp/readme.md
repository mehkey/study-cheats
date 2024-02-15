

https://cloud.google.com/products?hl=en

https://cloud.google.com/products?hl=en



https://passionatedevelopment.com/blog/2021/05/09/gcp-associate-cloud-engineer-cheatsheet/


https://cloud.google.com/compute/docs/general-purpose-machines#t2a_machines

## Compute

# VM

 You use the gcloud compute instances create command and include the --source-snapshot flag:
gcloud compute instances create VM_NAME \
  --source-snapshot BOOT_SNAPSHOT_NAME \
  --boot-disk-size BOOT_DISK_SIZE \
  --boot-disk-type BOOT_DISK_TYPE \
  --boot-disk-device-name BOOT_DISK_NAME
Google Cloud provides how-to guides to help users create a virtual machine (VM) instance at https://cloud.google.com/docs/overview/cloud-platform-services and https://cloud.google.com/compute/docs/instances/create-start-instance#console.

 For virtual hosting by IPs, virtual private networks (VPN), and load balancing, Compute Engine supports protocol forwarding for the following protocols:

    AH: Specifies the IP Authentication Header protocol
    ESP: Specifies the IP Encapsulating Security Payload protocol
    ICMP: Specifies the Internet Control Message Protocol
    SCTP: Specifies the Stream Control Transmission Protocol
    TCP: Specifies the Transmission Control Protocol
    UDP: Specifies the User Datagram Protocol

For private VIPs, only TCP and UDP are supported:

    TCP: Specifies the Transmission Control Protocol
    UDP: Specifies the User Datagram Protocol

Note: This is an exhaustive list of supported protocols. Only protocols that appear here are supported for protocol forwarding.
https://cloud.google.com/compute/docs/protocol-forwarding


Uses Instance groups to scale by creating instance templates


 Images can be created from four sources: disks, snapshots, cloud storage files, or another image. You can create disk images from the following sources:

    A persistent disk, even while that disk is attached to an instance
    A snapshot of a persistent disk
    Another image in your project
    An image that is shared from another project
    A compressed RAW image in Cloud Storage

https://cloud.google.com/compute/docs/images/create-delete-deprecate-private-images
https://cloud.google.com/compute/docs/import

 If you use the Cloud SDK tooling to deploy your app, such as gcloud app deploy, you can set the following autoscaling parameters in the app.yaml configuration file:

    min_instances
    max_instances
    target_throughput_utilization
    target_cpu_utilization

However, if you deploy using the appcfg tool from the App Engine SDK for Python 2, you cannot set those autoscaling parameters in the app.yaml configuration file. Instead, you must omit these parameters from the configuration file and set them directly in the API Explorer user interface, after deploying your app.

 When an image is marked obsolete, it is no longer available for use. An error message is returned if you try to use this image in a request. Existing links to this image are still allowed.
https://cloud.google.com/compute/docs/images/create-delete-deprecate-private-images


 The start method restarts an instance in a TERMINATED state, whereas methods such as reset and sudo reboot only work on instances that are currently running. Almost all instances can be restarted, as long as the instance is in a TERMINATED state.
https://cloud.google.com/compute/docs/instances/stop-start-instance


 The Cloud Monitoring agent is a collectd-based daemon that gathers system and application metrics from virtual machine instances and sends them to Monitoring. By default, the Monitoring agent collects disk, CPU, network, and process metrics. You can configure the Monitoring agent to monitor third-party applications to get the full list of agent metrics.
https://cloud.google.com/monitoring/agent

 An instance group is a collection of virtual machine (VM) instances that you can manage as a single entity. Compute Engine offers two kinds of VM instance groups, managed and unmanaged:

    Managed instance groups (MIGs) let you operate apps on multiple identical VMs. You can make your workloads scalable and highly available by taking advantage of automated MIG services, including autoscaling, autohealing, regional (multiple zone) deployment, and automatic updating.
    Unmanaged instance groups let you load balance across a fleet of VMs that you manage yourself.


# Cloud Run

Container as a service

# Appengine

# dataProc
Dataproc is a fully managed and highly scalable service for running Apache Hadoop, Apache Spark, Apache Flink, Presto, and 30+ open source tools and frameworks. Use Dataproc for data lake modernization, ETL, and secure data science, at scale, integrated with Google Cloud, at a fraction of the cost.

 Dataproc is priced at only 1 cent per virtual CPU in your cluster per hour, on top of the other Cloud Platform resources you use. In addition to this low price, Dataproc clusters can include preemptible instances that have lower compute prices, reducing your costs even further. Instead of rounding your usage up to the nearest hour, Dataproc charges you only for what you really use with second-by-second billing and a low, one-minute-minimum billing period.
https://cloud.google.com/dataproc/docs/concepts/overview


# Big Query BigQuery
 When you run a query, a temporary, cached results table is created in a special dataset referred to as an anonymous dataset. Unlike regular datasets that inherit permissions from the IAM resource hierarchy model (project and organization permissions), access to anonymous datasets is restricted to the dataset owner. The owner of an anonymous dataset is the user who ran the query that produced the cached result.
https://cloud.google.com/bigquery/docs/cached-results

Groups Batch queries
 BigQuery offers batch queries. BigQuery queues each batch query on your behalf and starts the query as soon as idle resources are available in the BigQuery shared resource pool. This usually occurs within a few minutes. If BigQuery hasn't started the query within 24 hours, BigQuery changes the job priority to interactive. Batch queries don't count toward your concurrent rate limit, which can make it easier to start many queries at once. Batch queries use the same resources as interactive (on-demand) queries.
https://cloud.google.com/bigquery/docs/running-queries

## Storages
## Big Table

 Cloud Bigtable is Google's NoSQL Big Data database service. It's the same database that powers many core Google services, including Search, Analytics, Maps, and Gmail.
https://cloud.google.com/bigtable/docs/schema-design-time-series



# Local SSD
 Local SSD (block) is the best GCP Cloud storage product for flash-optimized databases.  https://cloud.google.com/products/storage

# Persistent Disk

 When adding additional disk(s) through GCP, you can set the following parameters: Encryption Key Management, Source Image Type, and Disk Type.
https://cloud.google.com/compute/docs/instances/create-start-instance



# Cloud Storage
 Cloud Storage buckets allow an administrator to host a static website, and it’s recommended as the best solution.
https://cloud.google.com/storage/docs/hosting-static-website

 Objects stored in Cloud Storage have metadata associated with them. Metadata identifies properties of the object as well as specifies how the object should be handled when it's accessed. Metadata exists as key:value pairs.  There are two categories of metadata that users can change for objects:

    Fixed-key metadata: Metadata whose keys are set but for which you can specify a value
    Custom metadata: Metadata that you add by specifying both a key and a value associated with the key

When editing metadata, you should generally avoid non-ASCII characters because they are not permitted in HTTP headers, which the XML API uses. When you’re using the XML API, there is also a 16-KB limit to the combined size of the request URL and HTTP headers, so the total size of your metadata should take this limit into account.
https://cloud.google.com/storage/docs/metadata

 To rename an existing object in one of your Cloud Storage buckets, you can use the gsutil mv command: gsutil mv gs://BUCKET_NAME gs://BUCKET_NAME.

 Each lifecycle management configuration contains a set of rules. When defining a rule, you can specify any set of conditions for any action. If you specify multiple conditions in a rule, an object has to match all of the conditions for the action to be taken. If you specify multiple rules that contain the same action, the action is taken when an object matches the condition(s) in any of the rules. Each rule should contain only one action. A lifecycle rule specifies either a Delete action or a SetStorageClass action.
https://cloud.google.com/storage/docs/lifecycle


Google Cloud provides a variety of storage services including consistent, scalable, large-capacity data storage in Cloud Storage. Google Cloud uses persistent disks on Compute Engine for use as primary storage of instances. GCP Cloud Storage comes in several flavors: Standard Cloud Storage, Cloud Storage Nearline, Cloud Storage Coldline, and Cloud Storage Archive. Finally, Google Cloud offers fully managed NFS file servers in Filestore. Storage Services: https://cloud.google.com/docs/overview/cloud-platform-services and https://cloud.google.com/products/storage

 Signed URLs allow users to access resources for a limited or defined time.
https://cloud.google.com/storage/docs/access-control/signed-urls

 Objects stored in Cloud Storage have metadata associated with them. Metadata identifies properties of the object, as well as specifies how the object should be handled when it's accessed. Metadata exists as key:value pairs. You can edit the following metadata for objects, though you must have sufficient permission to do so: Access control metadata, Cache-Control, Content-Disposition, Content-Encoding, Content-Language, Content-Type, Custom-Time, Object holds.
https://cloud.google.com/storage/docs/metadata


# Filestore Datastore

 Cloud Datastore is the GCP service that is a NoSQL database. Cloud Firestore Datastore method that is a NoSQL document database built for automatic scaling, high performance, and ease of application development. It is the newest version of Datastore and introduces several improvements over Datastore.
https://cloud.google.com/appengine/docs/python/datastore/





## Network

# VPC 

Each VPC network implements a distributed virtual firewall that you can configure. Firewall rules allow you to control which packets are allowed to travel to which destinations. Every VPC network has two implied firewall rules that block all incoming connections and allow all outgoing connections. The default network has additional firewall rules, including the default-allow-internal rule, which permits communication among instances in the network. https://cloud.google.com/vpc/docs/overview

 Within GCP, a virtual private cloud (VPC) network’s internal IP addresses are accessible from the user’s on-premises network. The user does not need a NAT device or VPN tunnel to reach internal IP addresses. A VPC network is a virtual version of a physical network, implemented inside of Google's production network, using Andromeda. A VPC network provides the following:

    Provides connectivity for your Compute Engine virtual machine (VM) instances, including Google Kubernetes Engine (GKE) clusters, App Engine flexible environment instances, and other Google Cloud products built on Compute Engine VMs
    Offers native Internal TCP/UDP Load Balancing and proxy systems for Internal HTTP(S) Load Balancing
    Connects to on-premises networks using Cloud VPN tunnels and Cloud Interconnect attachments
    Distributes traffic from Google Cloud external load balancers to back ends

Projects can contain multiple VPC networks. Unless you create an organizational policy that prohibits it, new projects start with a default network (an auto mode VPC network) that has one subnetwork (subnet) in each region.
https://cloud.google.com/vpc/docs/vpc

## VPC modes

# Auto
 Unless you choose to disable it, each new project starts with a default network. The default network is an auto mode VPC network with prepopulated firewall rules. You can disable the creation of default networks by creating an organization policy with the compute.skipDefaultNetworkCreation constraint. Projects that inherit this policy won't have a default network.
https://cloud.google.com/vpc/docs/vpc#vpc_networks_and_subnets

# Custom
 When a custom mode VPC network is created, no subnets are automatically created. This type of network provides you with complete control over its subnets and IP ranges. You decide which subnets to create in regions that you choose by using IP ranges that you specify.
https://cloud.google.com/vpc/docs/vpc

# no Strict or strict



## Connectivity

# VPN
FOUR_IPS_REDUNDANCY
Explanation:
The HA VPN API contains an option for REDUNDANCY_TYPE, which represents the number of interfaces you configure for the external VPN gateway resource.
The gcloud commands automatically infer the following values of REDUNDANCY_TYPE from the number of interfaces you provide in the interface ID when you configure an external VPN gateway resource:

    One external VPN interface is SINGLE_IP_INTERNALLY_REDUNDANT.
    Two external VPN interfaces are TWO_IPS_REDUNDANCY.
    Four external VPN interfaces are FOUR_IPS_REDUNDANCY.

 The HA VPN API contains an option for REDUNDANCY_TYPE, which represents the number of interfaces you configure for the external VPN gateway resource.
The gcloud commands automatically infer the following values of REDUNDANCY_TYPE from the number of interfaces you provide in the interface ID when you configure an external VPN gateway resource:

    One external VPN interface is SINGLE_IP_INTERNALLY_REDUNDANT.
    Two external VPN interfaces are TWO_IPS_REDUNDANCY.
    Four external VPN interfaces are FOUR_IPS_REDUNDANCY.


https://cloud.google.com/network-connectivity/docs/vpn/how-to/creating-ha-vpn

 HA VPN is a high availability (HA) Cloud VPN solution that lets you securely connect your on-premises network to your virtual private cloud (VPC) network through an IPsec VPN connection in a single region. HA VPN provides an SLA of 99.99% service availability.
https://cloud.google.com/network-connectivity/docs/vpn/how-to/creating-ha-vpn

 Each VPC network has an associated dynamic routing mode that controls the behavior of all of its Cloud Routers. Cloud Routers share routes to your VPC network and learn custom dynamic routes from connected networks when you connect your VPC network to another network by using a Cloud VPN tunnel that uses dynamic routing, or by using Dedicated Interconnect or Partner Interconnect.

    Regional dynamic routing is the default. In this mode, routes to on-premises resources learned by a given Cloud Router in the VPC network apply only to the subnets in the same region as the Cloud Router. Unless modified by custom advertisements, each Cloud Router shares the routes only to subnets in its region with its on-premises counterpart.
    Global dynamic routing changes the behavior of all Cloud Routers in the network. The routes to on-premises resources that are learned globally are available in all subnets in the VPC network, regardless of region. Unless modified by custom advertisements, each Cloud Router shares routes to all subnets in the VPC network with its on-premises counterpart.

Routers use BGP
 Cloud Router isn't a connectivity option, but a service that works over Cloud VPN or Interconnect connections to provide dynamic routing by using the Border Gateway Protocol (BGP) for your VPC networks. Cloud Router isn't supported for Direct Peering or Carrier Peering connections.
https://cloud.google.com/network-connectivity/docs/router/how-to/configuring-bgp
https://cloud.google.com/network-connectivity/docs/router/concepts/overview

https://cloud.google.com/network-connectivity/docs/router/how-to/configuring-routing-mode

Dynamic by default
 When you create a Cloud Router, you can use its default route advertisements or specify custom advertisements. By default, Cloud Router advertises subnets in its region for regional dynamic routing or all subnets in a VPC network for global dynamic routing.
https://cloud.google.com/network-connectivity/docs/router/how-to/configuring-routing-mode
https://cloud.google.com/network-connectivity/docs/router/how-to/creating-routers


Explanation:
To create a forwarding rule that sends traffic to a single instance, you must do the following:

    Create a target instance. Your target instance is a single VM instance, but this instance can exist at the time you create the target instance, or it can be created afterward.
    Create a forwarding rule. Your target instance must exist before you create a forwarding rule. If incoming packets match the IP, protocol, and (if applicable) the port range that is being served by your forwarding rule, the forwarding rule directs that traffic to your target instance.

https://cloud.google.com/compute/docs/protocol-forwarding


 For HA VPN gateway, you configure an external peer VPN gateway resource that represents your physical peer gateway in Google Cloud. You can also create this resource as a standalone resource and use it later. To create an external peer VPN gateway, you need the following values from your physical peer gateway, which can also be a third-party software-based gateway. The values for the external peer VPN gateway resource must match the configuration on your physical peer gateway for the VPN to be established:

    The number of interfaces on your physical VPN gateway
    External IP address or addresses for the peer gateway(s) or interfaces
    BGP endpoint IP address(es)
    The IKE preshared key
    The ASN number

https://cloud.google.com/network-connectivity/docs/vpn/how-to/configuring-peer-gateway



# Peering

# Cloud Interconnect

 Cloud Interconnect provides low latency, high availability connections that enable you to reliably transfer data between your on-premises and Google Cloud virtual private cloud (VPC) networks. Also, Interconnect connections provide internal IP address communication, which means internal IP addresses are directly accessible from both networks.
https://cloud.google.com/network-connectivity/docs/interconnect/concepts/overview

(direct peering, CDN interconnect, carrier peering)

 If you are using Cloud Router with Partner Interconnect, you must specify ASN 16550.
Google Cloud provides how-to guides that help users create and manage networks at https://cloud.google.com/network-connectivity/docs/router/how-to/creating-routers

 Before you use Dedicated Interconnect, ensure that you meet the following requirements:

    Be familiar with basic network interconnections so that you can order and configure circuits.
    Be familiar with Cloud Interconnect terminology.
    Your network must physically meet Google's network in a colocation facility. You must provide your own routing equipment.

In the colocation facility, your on-premises network devices must support the following technical requirements:

    10-Gbps circuits, single mode fiber, 10GBASE-LR (1310 nm), or 100-Gbps circuits, single mode fiber, 100GBASE-LR4
    IPv4 link local addressing
    LACP, even if you're using a single circuit
    EBGP-4 with multi-hop
    802.1Q VLANs

Note: The maximum supported fiber length for 10GBASE-LR or 100GBASE-LR4 optics is 10 km. If your router is more than 10 km away from the Google demarcation, you must use a lit wavelength, DWDM, or other managed circuit to complete your connection.
https://cloud.google.com/network-connectivity/docs/interconnect/concepts/dedicated-overview

 Dedicated Interconnect connections support bandwidth Scale to meet the most demanding data needs. Connection capacity is delivered over one or more 10-Gbps or 100-Gbps Ethernet circuits, with a maximum of 8 × 10-Gbps (80 Gbps) circuits, or 2 × 100-Gbps (200 Gbps) circuits for each Dedicated Interconnect connection.
https://cloud.google.com/network-connectivity/docs/how-to/choose-product#cloud-interconnect
https://cloud.google.com/network-connectivity/docs/interconnect/quotas

## Load balancer

 Google Cloud offers the following load balancing features:

    single IP address to serve as the front end,
    automatic intelligent autoscaling of your backends,
    external load balancing for when your users reach your applications from the internet,
    internal load balancing for when your clients are inside of Google Cloud,
    regional load balancing for when your applications are available in a single region,
    global load balancing for when your applications are available across the world,
    pass-through load balancing (see also direct server return (DSR) or direct routing),
    proxy-based load balancing (as an alternative to pass-through),
    layer 4-based load balancing to direct traffic based on data from network and transport layer protocols, such as IP address and TCP or UDP port,
    layer 7-based load balancing to add content-based routing decisions based on attributes, such as the HTTP header and the uniform resource identifier, integration with Cloud CDN for cached content delivery.

https://cloud.google.com/load-balancing/docs/load-balancing-overview

 You can use traffic splitting to specify a percentage distribution of traffic across two or more of the versions within a service. Splitting traffic allows you to conduct A/B testing between your versions and provides control over the pace when rolling out features. Traffic splitting is applied to URLs that do not explicitly target a version.
https://cloud.google.com/appengine/docs/standard/java/splitting-traffic#gcloud or https://cloud.google.com/appengine/docs/standard/java/tools/uploadinganapp


The following underlying technologies enable Google Cloud Platform’s load balancer:  Google Front Ends (GFEs), Andromeda, Maglev, and Envoy proxy. 
https://cloud.google.com/load-balancing/docs/load-balancing-overview



## Pub Sub
 Google Cloud offers an asynchronous messaging services called Pub/Sub. This Big Data Service enables users’ applications to send messages as JSON data structures to a publishing unit called a topic. Big Data Services:
https://cloud.google.com/docs/overview/cloud-platform-services



## AI

# AI Platform

 AI Platform combines the managed infrastructure of Google Cloud with the power and flexibility of TensorFlow. You can use it to train your machine learning models at scale, and to host trained models to make predictions about new data in the cloud. AI Platform enables you to train machine learning models by running TensorFlow training applications on Google Cloud and hosts those trained models for you, so you can use them to get predictions about new data. AI Platform manages the computing resources that your training job needs to run, so you can focus more on your model than on hardware configuration or resource management.
Google Cloud offers a managed service called machine learning services. Machine Learning APIs: https://cloud.google.com/docs/overview/cloud-platform-services



# DialogFlow

Google Cloud offers a variety of APIs that enable you to take advantage of Google's ML without creating and training your own models. Dialogflow lets you build conversational interfaces for websites, mobile applications, popular messaging platforms, and IoT devices. You can use it to build interfaces, such as chatbots, that are capable of natural and rich interactions with humans. https://cloud.google.com/docs/overview/cloud-platform-services

# Cloud Trslation



# Cloud Vision



# Cloud Recognition





## Multi Cloud

# Anthos



## Data Transfer

# Data Transfer Service

 Data Transfer Services is a storage product used to collect research data, move machine language, artificial intelligence training datasets, and manage migration from S3 to Google Cloud.  Google Cloud provides a variety of storage services including consistent, scalable, large-capacity data storage in Cloud Storage. Google Cloud uses persistent disks on Compute Engine for use as a primary storage of instances. GCP Cloud Storage comes in several flavors: Standard Cloud Storage, Cloud Storage Nearline, Cloud Storage Coldline, and Cloud Storage Archive. Finally, Google Cloud offers fully managed NFS file servers in Filestore.
Storage Services - https://cloud.google.com/docs/overview/cloud-platform-services and https://cloud.google.com/products/storage



 Restricted ranges include Google public IP addresses and commonly reserved RFC ranges. Of the available IP addresses, the only restricted option is 199.36.153.4 because it is the Private Google Access–specific virtual IP address range.
https://cloud.google.com/vpc/docs/vpc


# Kubernetes

## GKE

 To create a Kubernetes cluster on GCP that can autoscale, the user creates the cluster and enables autoscaling as the cluster is created.
https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler
https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler

 The key components a cloud engineer would need to configure while using Google Kubernetes Engine are nodes, pods, services, clusters, and container images.
https://cloud.google.com/kubernetes-engine/docs/concepts/deployment
https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-architecture#nodes
https://kubernetes.io/docs/reference/kubectl/cheatsheet/

https://cloud.google.com/kubernetes-engine/docs/concepts/dashboards


 A status event is emitted periodically and describes the actual size of all autoscaled node pools and the target size of all autoscaled node pools as observed by the Cluster autoscaler.
https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-autoscaler-visibility

 The key components of a deployment set in the Create Deployment page in the Cloud Console include the Container Image, Cluster name, and Application name.
https://cloud.google.com/kubernetes-engine/docs/concepts/deployment
https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-architecture#nodes


# Deployment

## Deployment Manager
 Google Cloud Deployment Manager configuration must contain a resources section followed by the list of resources to create. Each resource must contain three components: name, type, and properties. More details can be found at  
https://cloud.google.com/deployment-manager/docs/fundamentals.

 Google Cloud Deployment Manager is an infrastructure deployment service that automates the creation and management of Google Cloud resources. You can write flexible template and configuration files and use them to create deployments that have a variety of Google Cloud services, such as Cloud Storage, Compute Engine, and Cloud SQL, configured to work together. Of the choices here, the key term infrastructure is the only solution as stated in the GCP documentation given software, hardware, and container are all too ambiguous. It’s also important to note that GCP Deployment Manager is a tool or service offered to help users at all level manage Google Cloud Service deployments more easily.
https://cloud.google.com/deployment-manager/docs

## Stackdriver

Stackdriver (now Cloud Monitoring) is GCP’s comprehensive monitoring, logging, and alerting product.
https://cloud.google.com/kubernetes-engine/docs/concepts/kubernetes-engine-overview

Comprehensive




## Observability

# Cloud Monitoring and logs

 Custom metrics are metrics defined by users. Custom metrics use the same elements that the built-in Cloud Monitoring metrics use:

    A set of data points.
    Metric-type information, which tells you what the data points represent
    Monitored-resource information, which tells you where the data points originated

Custom metrics can be used in the same way as built-in metrics. That is, you can create charts and alerts for your custom metric data.
https://cloud.google.com/monitoring/custom-metrics/creating-metrics

 Google’s Cloud Monitoring (formerly Stackdriver) performs notifications, monitoring, and logging in GCP Kubernetes Cluster.
https://cloud.google.com/kubernetes-engine/docs/concepts/kubernetes-engine-overview

 If you choose to split traffic to your application by cookies, the application looks in the HTTP request header for a cookie named GOOGAPPUID, which contains a value between 0 and 999:

    If the cookie exists, the value is used to route the request.
    If there is no such cookie, the request is routed randomly.

If the response does not contain the GOOGAPPUID cookie, the app first adds the GOOGAPPUID cookie with a random value between 0 and 999 before it is sent.
Using cookies to split traffic makes it easier to accurately assign users to versions. The precision for traffic routing can reach as close as 0.1% to the target split.
https://cloud.google.com/appengine/docs/standard/java/splitting-traffic#gcloud or https://cloud.google.com/appengine/docs/standard/java/tools/uploadinganapp


 For outgoing bandwidth, one way to reduce usage is to, whenever possible, set the appropriate Cache-Control header on your responses and set reasonable expiration times for static files. Using public Cache-Control headers in this way will allow proxy servers and your clients' browser to cache responses for the designated period of time. Incoming bandwidth is more difficult to control, since that's the amount of data your users are sending to your app. However, this is a good opportunity to mention DoS Protection Service, which allows you block traffic from IPs that you consider abusive.
https://cloud.google.com/appengine/docs/standard/python/console/managing-resources and https://cloud.google.com/appengine/docs/standard/php/config/appref

## Audit Logs

 Cloud Audit Logs return three types of logs:

    Admin activity logs: Contain log entries for operations that modify the configuration or metadata of a Compute Engine resource. Any API call that modifies a resource such as creation, deletion, updating, or modifying a resource using a custom verb falls into this category.
    System event logs: Contain log entries for system maintenance operations on Compute Engine resources.
    Data access logs: Contain log entries for operations that perform read-only operations that don't modify any data, such as get, list, and aggregated list methods. Unlike audit logs for other services, Compute Engine has only ADMIN_READ data access logs and doesn't generally offer DATA_READ and DATA_WRITE logs. The reason is that DATA_READ and DATA_WRITE logs are used only for services that store and manage user data such as Cloud Storage, Cloud Spanner, and Cloud SQL, and this doesn't apply to Compute Engine. There is one exception to this rule: instance.getSerialPortOutput does generate a DATA_READ log because the method reads data directly from the VM instance.

https://cloud.google.com/compute/docs/logging/audit-logging





# Security

## IAM

 To grant a role to a single member, you can also use the add-iam-policy-binding command. See the appropriate reference for more details:

    Projects: gcloud projects add-iam-policy-binding
    Folders: gcloud resource-manager folders add-iam-policy-binding
    Organizations: gcloud organizations add-iam-policy-binding

https://cloud.google.com/iam/docs/impersonating-service-accounts

To create a service account, at minimum the user must be granted the Service Account Admin role (roles/iam.serviceAccountAdmin) or the Editor basic role (roles/editor). You should not grant basic roles in a production environment, but you can grant them in a development or test environment. After you create a service account, you might need to wait for 60 seconds or more before you use the service account. If you try to use a service account immediately after you create it, and you receive an error, wait at least 60 seconds and try again. To create the service account, run the gcloud iam service-accounts create command: gcloud iam service-accounts create SERVICE_ACCOUNT_ID \
  --description="DESCRIPTION" \
  --display-name="DISPLAY_NAME"


WAIT 60 SECONDS
 To create a service account, at minimum, the user must be granted the Service Account Admin role (roles/iam.serviceAccountAdmin) or the Editor basic role (roles/editor). You should not grant basic roles in a production environment, but you can grant them in a development or test environment. After you create a service account, you might need to wait for 60 seconds or more before you use the service account. If you try to use a service account immediately after you create it, and you receive an error, wait at least 60 seconds and try again.
https://cloud.google.com/iam/docs/creating-managing-service-accounts



##  Google Cloud Deployment Manager ( Azure Blueprint, AWS CloudFormation)
 Google Cloud Deployment Manager is an infrastructure deployment service that automates the creation and management of Google Cloud resources. You can write flexible template and configuration files and use them to create deployments that have a variety of Google Cloud services, such as Cloud Storage, Compute Engine, and Cloud SQL, configured to work together. It’s also important to note that GCP Deployment Manager is a tool or service offered to help users at all levels manage Google Cloud Service deployments more easily.
A configuration describes all the resources you want for a single deployment. A configuration is a file written in YAML syntax that lists each of the resources you want to create and its respective resource properties. A configuration must contain a resources: section followed by the list of resources to create.
https://cloud.google.com/deployment-manager/docs
https://cloud.google.com/deployment-manager/docs/fundamentals


Contains Tempaltes
 A configuration can contain templates, which are essentially parts of the configuration file that has been abstracted into individual building blocks. After you create a template, you can reuse them across deployments as necessary. Similarly, if you find yourself rewriting configurations that share very similar properties, you can abstract the shared parts into templates. Templates are much more flexible than individual configuration files and intended to support easy portability across deployments.
https://cloud.google.com/deployment-manager/docs or https://cloud.google.com/deployment-manager/docs/fundamentals



## Labels (AWS and Azure Tags)

 When you deploy a VM solution from GCP Marketplace, the deployment is created with several default labels, which are a way to organize your deployments. Typically, the labels include a solution ID, and the partner ID. One of the labels is marketplace-suppress-benign-warnings, which blocks warnings that are typically not relevant for Cloud Marketplace solutions.
https://cloud.google.com/marketplace/docs and https://cloud.google.com/marketplace/docs/manage-deployments






## Stack Driver
 In GCP, when creating a Kubernetes Engine cluster, the following approaches are recommended as outlined in the Google Cloud how-to guides:  1. Use the Stackdriver Logging export feature to create a sink to BigQuery.  Specify a filter expression to export log records related to the Kubernetest cluster only 2. Turn on Stackdriver Logging during the Kubernetes Engine cluster creation. 
https://cloud.google.com/kubernetes-engine/docs/how-to/logging
https://cloud.google.com/logging/docs/export/configure_export_v2
https://kubernetes.io/docs/reference/labels-annotations-taints/









## Commands



When configuring policy routing in GCP Compute Engine VPC to support multiple network interfaces, what command does an administrator or user use via the command line?

gcloud compute ssh multinic-vm.

https://cloud.google.com/vpc/docs/create-use-multiple-interfaces

 To copy an object in one of your Cloud Storage buckets, you can use the gsutil cp command: 
 
 gsutil cp gs://BUCKET_NAME gs://BUCKET_NAME
https://cloud.google.com/storage/docs/copying-renaming-moving-objects


 On-demand queries are charged based on the number of bytes read. For current on-demand query pricing, see the Pricing page.
To estimate costs before running a query, you can use the following:

    Query validator in the Cloud Console
    --dry_run flag in the bq command-line tool
    dryRun parameter when submitting a query job using the API
    Google Cloud Pricing Calculator
    Client libraries

https://cloud.google.com/bigquery/docs/estimate-costs#estimating_query_costs


 You can create an auto mode network by using the following gcloud command:
gcloud compute networks create NETWORK \
 --subnet-mode=auto \
 --bgp-routing-mode=DYNAMIC_ROUTING_MODE \
 --mtu=MTU
Replace the placeholders with valid values:

    NETWORK is a name for the VPC network.
    DYNAMIC_ROUTING_MODE can be either global or regional to control the behavior of Cloud Routers in the network. For more information, refer to dynamic routing mode.
    MTU is the maximum transmission unit of the network. MTU can eiFloadther be 1460 (default) or 1500. Review the MTU information in the concepts guide before setting the MTU to 1500.



## redundant
The following services have one or more multiregional deployment areas in addition to any regional deployment areas: Datastore, Cloud Key Management Service, Cloud Storage, BigQuery, Cloud Spanner, Cloud Bigtable, Cloud Healthcare API.F


## Data flow dataflow

Google Cloud offers a managed service called DataFlow and a set of SDKs that users can use to perform batch and streaming data processing data. Big Data Services: https://cloud.google.com/docs/overview/cloud-platform-services

