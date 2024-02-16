# Dockerized httpd Web Server with Widget Factory Inc Website

## Introduction

This project provides a step-by-step guide to set up and run an Apache HTTP Server (httpd) in a Docker container. Additionally, it demonstrates how to integrate the Widget Factory Inc website into the httpd container. This allows you to easily deploy a web server and host a copy of the Widget Factory Inc website within a Dockerized environment.
Follow the instructions below to get started with viewing the default httpd page and then running a copy of the Widget Factory Inc website in the httpd container.

# Verify Docker Installation
```bash
docker ps
```
# Pull and Run httpd:2.4 Image
```bash
docker pull httpd:2.4
docker run --name httpd -p 8080:80 -d httpd:2.4
docker ps
```
# In a web browser, test connectivity to the container: 
```bash
http://<PUBLIC_IP_ADDRESS>:8080
```
# View default httpd page (First Run) 

![httpd](https://github.com/DimitryZH/content-widget-factory-inc/assets/146372946/ef5cd9a2-ba64-4210-8caa-e49cb13492ab)

# Clone Widget Factory Inc Repository
```bash
git clone https://github.com/linuxacademy/content-widget-factory-inc
cd content-widget-factory-inc
```
# Update httpd Container with Website Data
```bash
docker stop httpd
docker rm httpd
docker ps
docker run --name httpd -p 8080:80 -v $(pwd):/usr/local/apache2/htdocs:ro -d httpd:2.4
docker ps
```
# In a web browser, check connectivity to the container: 
```bash
(http://<PUBLIC_IP_ADDRESS>:8080)
```
# View updated httpd page with Widget Factory Inc content (Second Run)
![httpd-widget](https://github.com/DimitryZH/content-widget-factory-inc/assets/146372946/608beae7-50a1-4506-9e50-2d2e026e559b)
