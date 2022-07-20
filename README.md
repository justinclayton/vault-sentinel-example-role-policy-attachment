# Vault Sentinel Policy Example - Governing Role Policy Attachment

## Overview

This repo demonstrates a simple example of how to use HashiCorp Sentinel to govern which policies can be attached to a role in Vault. While this example refers to the Approle auth method, it can apply equally to Kubernetes auth method roles as well.

## What's in this repo

- `policy.sentinel` (the Sentinel policy itself)
- `test/policy/[good|bad].json` (mock requests)

## What does this policy do?

Using this policy, when an approle called "teamname-role" is being created/modified, Sentinel will ensure that each attached policy begins with the prefix "teamname-".

## Prerequisites

Use [these instructions](https://docs.hashicorp.com/sentinel/intro/getting-started/install) to download and install the standalone `sentinel` binary to enable local testing.

## Usage

From the top-level directory where the Sentinel policy is located, run `sentinel test`. This will perform testing against the mock requests contained in `test/policy/`.

From there you can add modify the policy and re-test, or add your own request examples as desired.

## Further Reading

- [Vault Sentinel Policies Guide (from HashiCorp Learn)](https://learn.hashicorp.com/tutorials/vault/sentinel)
- [Configure Sentinel for Vault (from Vault Documentation)](https://www.vaultproject.io/docs/enterprise/sentinel#using-sentinel)
- See what else you can do with Sentinel on Vault with more [Examples (from Vault Documentation)](https://www.vaultproject.io/docs/enterprise/sentinel/examples)