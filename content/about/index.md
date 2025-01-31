---
date: "2022-06-05"
description: Education, work experience and some of the technologies I recently used
title: About me
---

<div>
<div class="avatar" style="float: right; margin: 20px;"><img src="/images/avatar.jpg" alt="avatar"></div> I'm a Tech leader with strong background in both Software and DevOps engineering. I specialize in cloud platform architecture and release engineering, particularly focusing on Kubernetes-based deployments. I have experience leading engineering teams and coordinating technical initiatives across development and operations. My work spans from hands-on development to designing deployment solutions that serve multiple cloud environments.
</div>

- [Education](#education)
- [Experience](#experience)
  * [Piwik PRO (11.2015 - now)](#piwik-pro-112015---now)
    + [Staff Engineer (10.2021 - now)](#staff-engineer-102021---now)
    + [DevOps Team Lead (03.2020 - 06.2022)](#devops-team-lead-032020---062022)
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

### Staff Engineer (10.2021 - now)

As the principal technical position reporting directly to CTO, responsible for coordinating and consulting on solutions across all technical teams (around 60 engineers). Serve as technical arbiter in architectural decisions and represent engineering staff in business discussions. Drive company-wide technical initiatives focusing on: release engineering, documentation, CI, coding standards, cross-team cooperation, deployment pipeline, and FLOSS policy. Participate in strategic meetings requiring broad system knowledge, including high-profile client engagements and due diligence processes. Technical work comprises approximately 20% of time, primarily focused on deployment automation tooling (Go, Python, JavaScript, DevOps tools) and cross-team code review.

### DevOps Team Lead (03.2020 - 06.2022)

Leading a team of 5 DevOps engineers. Design and development of deployment and configuration management platform based on Kubernetes, terraform and helm, that runs Piwik PRO Analytics Suite (single infrastructure consists of ~400 pods, including applications and stateful components) on public clouds, private clouds, on-premises instances and development environments (as of Q1 2025 ~30 different infrastructures including 5 multi-tenant Azure public clouds, fully automated by terraform). Design of migration system, that allowed migrating the infrastructures from legacy, pre-kubernetes platform. The new platform is used by 4 development and 3 DevOps teams to deliver the software every two weeks for more than 3000 clients. Design and development of release and test automation frameworks for whole platform.

The team had no dedicated manager, so I performed also Engineering Manager role. It included handling cross-team dependencies, resolving potential conflicts within the team, negotiating salary changes with team members, planning self-development activities with team members, running all SCRUM meetings.

### DevOps Engineer (03.2019 - 03.2020)

Development of upgrade automation for Piwik PRO Analytics Suite, suitable to run on both Cloud and On-premise deployments. Led a small team of 3 people, that managed to solve the problem with long and error-prone manual upgrade documentation by replacing it with a simple system using python-based DSL, used to migrate ansible inventory variables and execute ansible playbooks. Participating in on-call rotation for multiple systems.

### Software Engineer (11.2015 - 03.2019)

Development of backend in Piwik PRO Analytics and Audience Manager modules in Python, Django and Tornado. This period includes also working for Piwik PRO's sister company - Clearcode.

## (03.2014 - 11.2015) Lightcode

### Fullstack Software Engineer

Developing solo and small team projects for various software house clients: www portal for local NGO organization in Django CMS , frontend for digital signage system in QT/C++, VR application for real estate agency in AngularJS 1.0 and three.js, medical facility automation in CakePHP, various smaller projects in CakePHP.

## (06.2012 - 03.2014) Freelancing

### Web Developer

A lot of small projects for individual clients, mostly in PHP, CakePHP and jQuery - hotel reservation software, comparison sites for financial products, helped in development of web-based game engine about breeding dogs (doggi-game.pl).


# Technologies

Some of the technologies I recently worked with, the list is not exhaustive:

* Programming languages
  * Go (advanced)
  * Python (advanced)
  * JavaScript (basic)
* Configuration management
  * Terraform (advanced)
  * Helm (advanced)
* CI/CD
  * Jenkins (advanced)
  * GitHub Actions (advanced)
* Kubernetes (from user perspective, advanced)
* Monitoring
  * Grafana (advanced)
  * Prometheus (intermediate)
* Databases
  * Clickhouse (from operator and developer perspective, advanced)
  * RabbitMQ (from operator and developer perspective, advanced)