# The GitOps Manifesto [wip]

> "GitOps is short for _Git Ops_. It is a name for a set of Ops practices using Git. The spirit of the name is to be like DevOps; something that anyone can do rather than being _a product_." - [Alexis Richardson](https://twitter.com/monadic)

While researching CI/CD workflows and DevOps practices for cloud native applications using _Microservices_, _Docker_ and _Kubernetes_,
I stumbled upon [GitOps](https://www.weave.works/blog/gitops-high-velocity-cicd-for-kubernetes).

I'm using this repo to create an overview of all things I'm learning about this subject.

## What is GitOps

GitOps builds on DevOps where Git is the single source of truth for for the desired state of
everything in your system; cluster, configuration, applications, tooling, etc.

## Why

We want to be able to reliably deliver quality software at a high velocity in order to innovate,
stand out in the market and be cost efficient.

> "When we say _high velocity_ we mean that every product team can safely ship updates many times a day — deploy instantly, observe the results in real time, and use this feedback to roll forward or back. The goal is for product teams to use [continuous experimentation](https://blog.acolyer.org/2017/09/29/the-evolution-of-continuous-experimentation-in-software-product-development/) to improve the customer experience as fast as possible." - [Alexis Richardson](https://twitter.com/monadic)

## How

First of all we must embrace the _DevOps mindset_. This doesn't mean having one or two people
calling themselves "DevOps Engineers", it means creating a culture where all stakeholders are
continuously collaborating around a set of shared goals in order to deliver software reliably and
fast. Adopting microservices can help with that, but only if the teams building them can take
_full ownership_ of the entire process. For one thing, this means we need to use tooling we're
comfortable with and can use efficiently. For example, as a developer I want to drive changes through
Git and have tools that allow me to observe the pushed results.

> “Ideally if I make a code change, all I want is a URL to tell me where it’s running. You get bonus points if you can give me metrics to tell me how well it’s running." - [Kelsey Hightower](https://twitter.com/kelseyhightower)

GitOps fits perfectly in this type of workflow, where _Git_ becomes the source of truth of the
_desired state_ of the system and _Obersvability_ becomes the source of truth of the _actual running state_
of the system. Using the _Operator Pattern_ the actual state can be controlled to reflect the desired
state, by listening to (certain) Git tags to be pushed and orchestrate service deployments to the
cluster in a continuous loop. Tools like [Weaveworks Flux](https://github.com/weaveworks/flux)
achieve this.

Effectively GitOps allows for **operations by Pull Request**.

## Requirements

1.  [Declarative infrastructure as code](https://www.thoughtworks.com/insights/blog/infrastructure-code-reason-smile)
2.  Code & config version controlled in Git
3.  Completely automated delivery pipeline
4.  Observable & monitorable services

## Resources

### Blog Posts

* [GitOps - Operations by Pull Request](https://www.weave.works/blog/gitops-operations-by-pull-request)
* [The GitOps Pipeline - Part 2](https://www.weave.works/blog/the-gitops-pipeline)
* [GitOps Part 3 - Observability](https://www.weave.works/blog/gitops-part-3-observability)
* [GitOps Part 4 - Application Delivery Compliance and Secure CICD](https://www.weave.works/blog/gitops-compliance-and-secure-cicd)
* [GitOps: High velocity CICD for Kubernetes](https://www.weave.works/blog/gitops-high-velocity-cicd-for-kubernetes)

### Videos

* [KubeCon 2017 Opening Keynote - Kelsey Hightower, Google](https://www.youtube.com/watch?v=07jq-5VbxBVQ)
* [KubeCon 2017 - GitOps - Operations by Pull Request - Alexis Richardson, Weaveworks & William Denniss, Google](https://www.youtube.com/watch?v=BSqE2RqctNs)

### Tooling

* [Weaveworks Flux](https://github.com/weaveworks/flux)
* [Weaveworks Kubediff](https://github.com/weaveworks/kubediff)
* [Bitnami Sealed Secrets](https://github.com/bitnami-labs/sealed-secrets)
