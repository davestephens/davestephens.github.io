---
layout: page
title: CV
permalink: /cv/
---

I've worked in the financial services industry most of my career, with companies such as Goldman Sachs and more recently 
Credit Suisse. Putting it simply, I specialise in getting stuff done. I sit right in the middle of a bunch of agile
development teams, and I help them to get their _own_ stuff done quicker and better than they could if I wasn't there. 

If you're not into reading long resumes, read the following few bullets for a whistle-stop tour of what I'm good at:

* Linux (RHEL, Ubuntu) and Windows Server administration.
* Deployment and configuration management with Ansible.
* Scripting with Bash, Powershell, Batch.
* Development with Ruby, Ruby on Rails. Hacking on anything else thrown my way. 
* Monitoring servers and applications with tools such as Collectd, Graphite, Splunk, Monit, Consul, Nagios.
* CI with TeamCity, version control with Git, SVN, Stash, Github Enterprise.
* Multi-region team management, including hiring, performance reviews, objective setting, workforce reduction

You can download the full version [here][cv].

# Employment History

## Credit Suisse - January 2015 - present

### Vice President, Platform & DevOps Engineer, Equities Risk
I run DevOps (i.e. "Getting Stuff Done") for the Equities Risk division. 

* Management of a 1000+ server estate consisting of both physical and virtual servers, split approximately 85% Linux,
 15% Windows.
* Configuration management of infrastructure and deployment of software using Ansible.
* Physically located within an Agile dev team - involved in multiple daily team standups, production issues, 
iteration planning. Work closely with devs and operations teams to attempt to break down traditional banking “siloed”
 roles.
* Monitoring and capacity analysis using Collectd, Graphite, Graphana, Monit, Nagios. Built relevant dashboards to 
monitor JVM & HTTP based applications. Understand the intricacies between monitoring VMs and physical hardware.
* Maintenance of deployment scripts in Ruby, deploying to both Linux and Windows hosts. 
* Performance tweaking of Windows and Linux infrastructure to maximise throughput for JVM & HTTP based applications.

Some of the larger projects in this role:

* Managed and executed replacement of 600 virtual RHEL Linux servers and application migration to 150 physical 
servers, for purposes of cost reduction, reliability and performance consistency. Post provisioning configuration and consistency checks were carried out via Ansible. Servers were split for use by multiple services using c-groups. 
* Development of automated deployment tool for dev, UAT and production environments using Teamcity and Ansible. 
Allows new services to be deployed and released simply by developers including an Ansible playbook within a build package. 
* Development of a service “baseline”, consisting of a repeatable set of tools for use by new services; Ansible 
for deployment, Collectd and Graphite/Graphana for metrics, Splunk for log collection, Nagios/Monit for monitoring 
and Consul for service discovery.


## Credit Suisse - May 2011 - December 2014

### AVP, Environment & Release Management, Equity Derivatives
I managed the Release and Environment Management team at Credit Suisse, a team of eight, split across multiple 
regions. The team is responsible for all software released into the Equity Derivatives division, the infrastructure
 that it runs on, and the infrastructure used to develop it.

My role was extremely varied, but not limited to: 

* Capacity and platform management - provisioning, decommissioning, capacity analysis. I lead the project to 
introduce Nagios into Credit Suisse, which now monitors the entire Equity Derivatives estate.
* Technical consultancy - I worked closely with development teams to help them to select the best technology 
and infrastructure for their application. This often involved introducing new previously-unapproved technology 
into the bank and arranging approval for use.
* Strategic software development to assist my day to day role, e.g. scripting large scale software deployments 
across multiple platforms.
* Release management - deploying the software produced by various development teams with Equity Derivatives IT. 

I ran the team borrowing practises from common agile development methodologies. Rather than a weekly team meeting,
 we had daily stand-ups and monthly retrospectives. With the high turnover of work, this allowed me to keep on top
  of the teams’ upcoming deliverables ensuring targets were met.


## Credit Suisse – July 2009 – May 2011

### AVP, High Performance Computing, Derivatives IT
Working within a small team, I was responsible for an estate of over 3000 mission-critical servers used to 
calculate intra-day and nightly risk for all key business units within the bank.

* Day to day management of a 3500 server estate, utilising custom-written scripts to assist in management and 
fire-fighting.
* Implemented Splunk for capturing of logs and performance metrics of servers in the grid.
* Wrote a custom Powershell module to assist team members in managing grid nodes. 
* Deployed Platform Symphony to replace in-house written grid scheduling software. 

## Goldman Sachs – January 2006 – May 2009

### System Analyst
Working within a team of five I was responsible for 3rd line support of all Windows Server infrastructure within 
Goldman Sachs EMEA.

* Maintaining approx 5500 Windows XP workstations, 1000 Windows 2003 mission critical servers, including patching, 
performance monitoring (using custom perfmon scripts) and application deployment.
* Project managed two new office setups from a Windows Infrastructure perspective. Included designing workstation 
builds and writing group policies to suit. 


## Alea Group PLC – June 2005 - January 2006

### Technical Analyst
Working within a team of five I was responsible for 3rd line support of a 70 server and 160 user Windows 2000 / 2003 
Active Directory network, and was technical lead on a large proportion of Alea’s system project work.


## Rank Group PLC – December 2003 - June 2005

### Technical Analyst
Working within a team of six Support Analysts, I was responsible for the 2nd and 3rd line support and maintenance of 
a 5000 user, 160 site Windows 2003 Active Directory network.
 
 
## VEGA Group PLC – June 2003 - December 2003

### Technical Analyst
My first job after leaving university, working within a team of three I was responsible for the computer support of 
50 on-site users as well as approximately 150 mobile users.
 
# Education 

## University of Kent at Canterbury - October 1999 – May 2003 
Multimedia Technology and Design - First Class with Honours
  
## Sandhurst School - September 1992 – September 1999
3 A-Levels, 10 GCSEs
  
[cv]: https://docs.google.com/document/d/1GTB0GuF9VpWxTfLQcsPUUfO-cCHyz_XnTXCtZBQlgdg
