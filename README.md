# PAGNCstack

### Docker Monitoring Stack with [Prometheus](https://prometheus.io/), [Grafana](http://grafana.org/), [cAdvisor](https://github.com/google/cadvisor), [NodeExporter](https://github.com/prometheus/node_exporter) and [AlertManager](https://prometheus.io/docs/alerting/latest/alertmanager/)

A comprehensive monitoring solution for Docker hosts and containers, utilizing Prometheus, Grafana, cAdvisor, NodeExporter, and AlertManager for alerting.

## Install

Clone this repository on your Docker host, navigate to the directory, and run the compose command:

```bash
git clone https://github.com/Divya4242/PAGNCstack.git
cd PAGNCstack
```
Prerequisites

• Docker Engine >= 1.13

• Docker Compose >= 1.11

## Setup AlertManager
Follow the steps in the alertmanager folder's [README.md](https://github.com/Divya4242/PAGNCstack/blob/main/alertmanager/readme.md) file before running Docker Compose.

## Run Docker Compose
```
docker-compose -f docker-compose.yml up -d
```
## Setup Grafana
![image](https://github.com/Divya4242/PAGNCstack/assets/113757574/26c2b9d7-2838-4fb4-8b24-a72f92146074)

1. Ensure all targets are up as shown in the image above.

![image](https://github.com/Divya4242/PAGNCstack/assets/113757574/d8c63e07-b355-4fdd-8bd2-350be396cd04)

2. Go to Grafana and add the Prometheus data source:
   
    • Add the Prometheus server URL in the connection settings as shown in the image above.

    • Click the "Save & Test" button at the bottom of grafana page.

![image](https://github.com/Divya4242/PAGNCstack/assets/113757574/33ddecf2-b32b-4b45-834a-d6b7864c4595)

3. Once the data source is successfully added, import the dashboard:

    • Go to Dashboards -> Import -> Import via Dashboard JSON.
    • Paste the contents of [dashboard.json](https://github.com/Divya4242/PAGNCstack/blob/main/grafana/dashboard.json) from the Grafana folder in this repository.

## Dashboard Photos
![image](https://github.com/Divya4242/PAGNCstack/assets/113757574/abe4ecf6-26f0-46e6-ba11-3f9d82a99eba)
![image](https://github.com/Divya4242/PAGNCstack/assets/113757574/27817fe7-a7d7-488a-b367-b86cee0493d6)
![image](https://github.com/Divya4242/PAGNCstack/assets/113757574/88399da5-959a-40cf-bffd-237bfa4ddf77)


#### By following these steps, you can set up a robust monitoring stack for your Docker environments, providing insights and alerts to keep your services running smoothly.



