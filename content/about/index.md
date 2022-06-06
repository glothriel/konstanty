---
date: "2022-06-05"
description: Education, work experience and some of the technologies I recently used
title: About me
---

<div>
<div class="avatar" style="float: right; margin: 20px;"><img src="/images/avatar.jpg" alt="avatar"></div> I'm a Tech leader and DevOps engineer with strong software engineering background. I specialize in configuration management of Kubernetes applications and release engineering. I have successfully led teams consisting of multiple senior engineers coming from both sysadmin and software engineering background.
</div>

- [Education](#education)
- [Experience](#experience)
  * [Piwik PRO (11.2015 - now)](#piwik-pro-112015---now)
    + [Principal Engineer (10.2021 - now)](#principal-engineer-102021---now)
    + [DevOps Tech Lead (03.2020 - 06.2022)](#devops-tech-lead-032020---062022)
    + [DevOps Engineer (03.2019 - 03.2020)](#devops-engineer-032019---032020)
    + [Software Engineer (11.2015 - 03.2019)](#software-engineer-112015---032019)
  * [(03.2014 - 11.2015) Lightcode](#032014---112015-lightcode)
    + [Fullstack Software Engineer](#fullstack-software-engineer)
  * [(06.2012 - 11.2015) Freelancing](#062012---112015-freelancing)
    + [Web Developer](#web-developer)
- [Technologies](#technologies)


# Education

Bachelor Computer Scientist, graduated Wrocław University of Technology in 2014.

# Experience

## Piwik PRO (11.2015 - now)

### Principal Engineer (10.2021 - now)

Coordination and consultation of solutions for all technical teams in the company (around 40 people in total), being the decisive person in technical disputes, being a primary representative of technical staff when communicating with business, shaping most of the technical cross-team efforts in the company, especially the ones involving day-to-day work: release engineering, CI, CD, coding standards, cross-team cooperation, deployment pipeline, FLOSS policy. Participating in meetings, that the broadest knowledge of the system is required - high profile clients, due diligence processes. Strictly technical responsibilities include coding (around 30% of time, almost exclusively around deployment automation tooling - go, python, javascript and a lot of DevOps tools) and cross-team code review. The role is internally called "Architect".

### DevOps Tech Lead (03.2020 - 06.2022)

Design and development of deployment and configuration management platform based on Kubernetes, terraform and helm, that runs Piwik PRO Analytics Suite (single infrastructure consists of ~400 pods, including applications and stateful components) on public clouds, private clouds, on-premises instances and development environments (as of Q2 2022 12 different infrastructures). Design of migration system, that allowed migrating the infrastructures from previous platform, based on ansible and Rancher 1.6 (pre-kubernetes). The platform is used by 4 development and 3 DevOps teams to deliver the software every two weeks for more than 3000 clients. Design and development of release and test automation frameworks for whole platform. I was a member of a team that was responsible for obtaining SOC-2 certification, I contributed a lot of ideas and their implementation (automated nightly trivy scans and short slack reports with the results, optional falco deployments and alerts, alerts based on access logs, immutable logs storage, auto-expiration of extended privileges for developers debugging on production), that helped with obtaining the certificate.

### DevOps Engineer (03.2019 - 03.2020)

Development of upgrade automation software for Piwik PRO Analytics Suite. Led a small team of 3 people, that managed to solve the problem with long and error-prone manual upgrade instructions by replacing them with a simple system using python-based DSL, used to migrate ansible inventory variables and execute ansible playbooks. Participating in on-call rotation for multiple systems.

### Software Engineer (11.2015 - 03.2019)

Development of backend in Piwik PRO Analytics and Audience Manager modules in Python, Django and Tornado. This period includes also working for Piwik PRO's sister company - Clearcode.

## (03.2014 - 11.2015) Lightcode

### Fullstack Software Engineer

Developing solo and small team projects for various software house clients: www portal for local NGO organization in Django CMS , frontend for digital signage system in QT/C++, VR application for real estate agency in AngularJS 1.0 and three.js, medical facility automation in CakePHP, various smaller projects in CakePHP.

## (06.2012 - 11.2015) Freelancing

### Web Developer

A lot of small projects for individual clients, mostly in PHP, CakePHP and jQuery - hotel reservation software, comparison sites for financial products, helped in development of web-based game engine about breeding dogs (doggi-game.pl).


# Technologies

Some of the technologies I recently worked with:

|              | |
|-----------------------------------|--------------------------------------------------------|
| Programming languages             | Go, Python                                             |
| Frameworks                        | Fasthttp, Django, Nolar/kopf, Pytest                           |
| Clouds                            | Azure, OVH, OpenStack                                  |
| IAAC Tools                        | Terraform, FluxCD                                      |
| Kubernetes                        | Helm, Kubernetes operators                             |
| Security                          | Aqua Trivy, Fairwinds Polaris, Falco                   |
| Misc                              | Travis, Github Actions, Jenkins, MinIO, HAProxy, Nginx |
| Monitoring                        | Prometheus, Grafana, Loki, PagerDuty, Alertmanager     |
| Databases (usage and maintenance) | RabbitMQ, Redis, Clickhouse, MySQL, Consul, Zookeeper  |
|              | |
