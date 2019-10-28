### Prometheus with Grafana
•  Building a Grafana metrics dashboard using prometheus data source with nodeJS monitoring.

•  This is to be used to monitor to processors of nodejs in all the microservices running on a cluster.

•  NodeJS to be monitored

•  Using functions

•  Microservices 

•  Exporting data from mongodb-exporter to prometheus to grafana

• kubectl delete namespace monitoring

### Links to Helm charts for implementing prometheus in grafana
• Time- series database blog https://blog.timescale.com/blog/what-the-heck-is-time-series-data-and-why-do-i-need-a-time-series-database-dcf3b1b18563/

• Node-exporter helm chart
https://github.com/helm/charts/tree/master/stable/prometheus-node-exporter
• MongoDB-exporter helm chart
https://github.com/helm/charts/tree/master/stable/prometheus-mongodb-exporter

• Prometheus-operator helm chart
https://github.com/helm/charts/tree/master/stable/prometheus-operator
• Trying Prometheus Operator with Helm + Minikube
https://medium.com/faun/trying-prometheus-operator-with-helm-minikube-b617a2dccfa3
• Percona Monitoring and Management (PMM) Graphs
https://www.percona.com/blog/2017/03/10/percona-monitoring-and-management-pmm-graphs-explained-custom-mongodb-graphs-metrics/
• Mongodb monitoring - https://docs.mongodb.com/manual/administration/monitoring/
Notes from - https://medium.com/thron-tech/how-we-implemented-red-and-use-metrics-for-monitoring-9a7db29382af

### The Four Golden Signals
The Four Golden Signals are a series of metrics defined by Google Site Reliability Engineering that are considered the most important when monitoring a user-centric system:
* Latency : The time it takes to service a request;
* Traffic : A measure of how much demand is being placed on the system;
* Errors : The rate of requests that fails;
* Saturation : How “full” our service is, basically how close we are to exhausting system resources;
We don’t use exactly those 4 metrics but we choose to work with two different methods using a subset of metrics generated from these four, depending on what we are monitoring: for HTTP Metrics we use the RED Method while we use the USE Method for Infrastructure.
### From the Four Golden signals to the RED way of creating Metrics
The RED method is a subset of “The Four Golden Signals” that’s focused on micro-service architectures and which includes these metrics:
* Rate: the number of requests our service is serving per second;
* Error: the number of failed requests per second;
* Duration: the amount of time it takes to process a request;
Measuring these metrics is pretty straightforward, especially with tools like Prometheus, and using the same metrics for every service helps us create a standard and easy-to-read format for dashboards that have to show the results.

Using the same metrics for every service and treating them the same way, from a monitoring perspective, helps the scalability in the operations teams, reduces the amount of service-specific training the team needs, and reduces the service-specific special cases the on-call-engineers need to remember for those high-pressure incident response scenarios — what is referred to as “cognitive load.”
### Infrastructure and the USE method
The USE Method is more focused on infrastructure monitoring where you have the keep the physical resources under control and is based on just three parameters:
* Utilization: the proportion of the resource that is used, so 100% utilization means no more work can be accepted;
* Saturation: the degree to which the resource has extra work which it can’t service, often queued;
* Errors: the count of error events;
While this method at start helped us identify which specific metrics to use for each resource (CPU, Memory, Discs, …), our next task was to interpret their values, and it’s not always so obvious.

### https://medium.com/google-cloud/1-hour-migrations-1-sqs-to-gcps-cloud-pub-sub-105bcac63318
