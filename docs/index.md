---
page_title: "Provider: Athenz"
subcategory: ""
description: |-
Athenz Terraform provider for interacting with Athenz API.
---

# Athenz Provider

## Background

As a part of simplifying and improving Athenz user experience, we would like to offer our customers Infrastructure As Code capability.

Terraform relies on plugins called "providers" to interact with cloud providers, SaaS providers, and other APIs.

Each provider adds a set of resource types and/or data sources that Terraform can manage. Every resource type is implemented by a provider; without providers, Terraform can't manage any kind of infrastructure.

## Concepts
Each provider adds a set of resource types and/or data sources that Terraform can manage.
Every resource type is implemented by a provider; without providers, Terraform can't manage any kind of infrastructure.

## Data source
Data sources allow Terraform use information defined outside of Terraform, defined by another separate Terraform configuration, or modified by functions.

## Resources
Resources are the most important element in the Terraform language. Each resource block describes one or more infrastructure objects.

## Example Usage

Do not keep your authentication password in HCL for production environments, use Terraform environment variables.

To install this provider, copy and paste this code into your Terraform configuration. Make sure to update the version parameter to appropriate value. Then, run `terraform init`.

You can also obtain this snippet from the [provider home page](https://registry.terraform.io/providers/AthenZ/athenz/latest) by clicking the "USE PROVIDER" button on top right hand side.

```terraform

terraform {
  required_providers {
    athenz = {
      source = "AthenZ/athenz"
      version = "<_VERSION_HERE_>"
    }
  }
}

provider "athenz" {
  zms_url = "https://athenz.url"
  cacert = "<ca-cert-path>"
  cert = "<certificate-path>"
  key = "<key-path>"
}
```

## Schema

### Required

- **zms_url** (String) Athenz API URL
- **cert** (String) Certificate path - required for the zms client
- **key** (String) Key path - required for the zms client

### Optional

- **cacert** (String, Optional) CA Certificate path - relevant in some cases for the zms client
