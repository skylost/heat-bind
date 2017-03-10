Heat template for bind
======================

Heat is a service to orchestrate multiple composite cloud applications using
templates

This repository provides:

* bind for designate

ENV
---
Create environment file (bind.yml) with the following variables:

* key_name:
* image:
* flavor: 2
* net_id:
* fixed_ip_1:
* fixed_ip_3:
* remote_ip_prefix:
* virtualenv_url:
* keystone_url:
* monasca_agent_user:
* monasca_agent_password:
* monasca_agent_project:
* monasca_agent_dimensions:
* monasca_api_url:
* barbican_uri_token_id:
* barbican_uri_bind_tsig:

RUN
---
git clone git@vm-gitlab-01:heat/bind.git && cd templates
heat --os-tenant-id c755f5c0d81940318edacf8c8552aa3a stack-create -f bind.hot -e bind.yml bind

DELETE
------
heat --os-tenant-id c755f5c0d81940318edacf8c8552aa3a stack-delete bind
