# Etcd-Terraform Example

This repo is a demonstration of creating self-discovering Etcd clusters
with Terraform.

Google is the cloud provider used here, but any other cloud provider
supported by both CoreOS and Terraform would work just as well (e.g. AWS).

For more background information, see
[here](http://maxenglander.com/2015/06/09/etcd-clusters-with-terraform.html).

## Requirements

 1. Terraform
 1. A Google Cloud account

## Setup

 1. Clone this repo
 1. Log in to your Google Cloud account
 1. Create a new project, e.g. "etcd-terraform"
 1. Enable the Google Compute API for the project
 1. Create a New Client ID (service account)

The last step will provide you with the credentials you will need to
authenticate with Google Cloud via Terraform. Put them somewhere safe.

## Configure Terraform

In your local clone of this repo, you will need to update `terraform.tfvars.json`
with your Google Project ID and the path to your credentials.

## Boot Cluster

To boot the cluster, simply run the following inside your local clone of this repo.

    $ terraform apply

## Notes

The `etcd_discovery_url.txt` is purposefully empty. Terraform complains if you try
to read with `${file(...)}` from a non-existent file.
