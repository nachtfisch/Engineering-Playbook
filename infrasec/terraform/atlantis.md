# [Terraform](README.md) / Atlantis

We're beginning to use Atlantis throughout projects at Truss. There's more to come, but for now here are some helpful things to know.

## Tips and gotchas

* When resetting a GitHub personal token in Parameter Store, you will have to redeploy the Atlantis instance. Otherwise, the new credential will not be updated in the instance.
* We use [this](https://github.com/terraform-aws-modules/terraform-aws-atlantis) Atlantis terraform module to spin up our instances. If you do not set the `atlantis_image` variable, you'll find `atlantis:latest` is used by default. This default is not recognized as updated when a new "latest" is released due to the word remaining unchanged. Therefore, we recommend you pass in a numbered version of the Atlantis docker image to the `atlantis_image` var.

## Links and other reading

* [Truss's Atlantis blog post](https://truss.works/blog/infrastructure-management-with-atlantis)
* :lock: [Atlantis setup in Truss's commercial accounts for the prod tiers](https://github.com/trussworks/legendary-waddle)
* :lock: [Atlantis setup in Truss's commercial accounts for the dev tiers](https://github.com/trussworks/legendary-waddle-dev)
