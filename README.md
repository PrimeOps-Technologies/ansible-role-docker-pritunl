Role Name
=========
# Ansible Role: Grafana-Prometheus-Node Exporter
[![PrimeOps-Technologies](https://img.shields.io/badge/Made%20By-PrimeOps-blue?style=flat-square&logo=ansible)](https://primeops.co.in)
[![Ansible](https://img.shields.io/badge/Ansible-2.9%2B-green.svg?logo=ansible)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)

An Ansible role that installs and configures **Grafana**, **Prometheus**, and **Node Exporter** to provide a self-hosted monitoring and metrics stack.

---
## 🏢 About PrimeOps-Technologies
**PrimeOps-Technologies** delivers **Cloud & DevOps excellence** for modern teams:
- 🚀 **Infrastructure Automation** with Terraform, Ansible & Kubernetes
- 💰 **Cost Optimization** via scaling & right-sizing
- 🛡️ **Security & Compliance** baked into CI/CD pipelines
- ⚙️ **Fully Managed Operations** across AWS, Azure, and GCP

> 💡 Need enterprise-grade DevOps automation?
> 👉 Visit [**primeops.co.in**](https://primeops.co.in) or email **primeopstechnologies@gmail.com**

## 📁 Directory Structure

```
nginx-php7.4/
├── defaults/main.yml
├── handlers/main.yml
├── meta/main.yml
├── tasks/main.yml
├── templates/nginx.conf.j2
├── templates/index.php
└── LICENSE
```

Requirements
------------
* **Ansible** 2.9 or newer
* **Supported OS**
    * Ubuntu 20.04 / 22.04
    * Debian 10 / 11


## ⚙️ Role Variables

### **defaults/main.yml**
```yaml
# Pritunl variable
pritunl_version: "latest"

# Pritunl settings
pritunl_path: "/opt/pritunl"
pritunl_log: "/var/log/pritunl.log"
pritunl_user: pritunl
pritunl_group: pritunl

# Mongo settings
mongo_path: "/opt/pritunl/mongo"
mongo_user: mongo
mongo_group: mongo

```

---

## 🚀 Usage

---

## 📄 pritunl Template (pritunl.conf)

```pritunl.conf
{
    "mongodb_uri": "mongodb://localhost:27017/pritunl",
    "server_key_path": "/var/lib/pritunl/pritunl.key",
    "log_path": "{{ pritunl_log }}",
    "static_cache": true,
    "server_cert_path": "/var/lib/pritunl/pritunl.crt",
    "temp_path": "/tmp/pritunl_%r",
    "bind_addr": "0.0.0.0",
    "debug": false,
    "www_path": "/usr/share/pritunl/www",
    "local_address_interface": "auto"
}

```

---

## 🔄 Handlers

```yaml
- name: restart pritunl
  service:
    name: pritunl
    state: restarted
    enabled: true

- name: reload pritunl
  service:
    name: pritunl
    state: reloaded
    enabled: true

- name: start pritunl
  service:
    name: pritunl
    state: started
    enabled: true
```

---

## 🧪 Testing

After running the role, verify using:

```
https://your-server-ip/
```

---

## 🖥️ Supported Platforms

| OS | Versions                  |
|----|---------------------------|
| **Ubuntu** | 18.04, 20.04, 22.04 24.04 |
| **Debian** | 10, 11                    |

## 👥 Team Members
<table> <tr> <td align="center"> <img src="https://github.com/yrahul05.png" width="80" style="border-radius:50%"><br> <strong>Rahul Yadav</strong><br> <sub>CEO & CTO</sub><br> <a href="https://github.com/yrahul05">@yrahul05</a> </td>  <td align="center"> <img src="https://github.com/themanojkumawat.png" width="80" style="border-radius:50%"><br> <strong>Manoj Kumawat</strong><br> <sub>DevOps Lead</sub><br> <a href="https://github.com/themanojkumawat">@themanojkumawat</a> </td> <td align="center"> <img src="https://github.com/sureshyadav76.png" width="80" style="border-radius:50%"><br> <strong>Suresh Yadav</strong><br> <sub>Senior DevOps Engineer</sub><br> <a href="https://github.com/sureshyadav76">@sureshyadav76</a> </td> <td align="center"> <img src="https://github.com/therahul28.png" width="80" style="border-radius:50%"><br> <strong>Rahul</strong><br> <sub>Senior DevOps Engineer</sub><br> <a href="https://github.com/therahul28">@therahul28</a> </td> <td align="center"> <img src="https://github.com/abhisharma24.png" width="80" style="border-radius:50%"><br> <strong>Abhi Sharma</strong><br> <sub>Senior DevOps Engineer</sub><br> <a href="https://github.com/abhisharma24">@abhisharma24</a> </td> <td align="center"> <img src="https://github.com/Rohityadav-7.png" width="80" style="border-radius:50%"><br> <strong>Rohit Yadav</strong><br> <sub>COO</sub><br> <a href="https://github.com/Rohityadav-7">@Rohityadav-7</a> </td>  </tr> </table>


### 💙 Maintained by [PrimeOps-Technologies](https://primeops.co.in)
> PrimeOps-Technologies — Simplifying Cloud, Securing Scale.
