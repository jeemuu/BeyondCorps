# BeyondCorps

This repository provides a short description of the BeyondCorp security model and resources for implementing this model at your organization.

## Introduction

"BeyondCorp" is a Zero Trust¹ security framework initially created by Google. It challenges the idea of perimeter security in the form of network segmentation in order to separate "outsiders" from trusted employees.

The issue with perimeter security is that it assumes everyone inside the network is trused and everyone outside the network is not! This can be false in two aspects; you can have an intruder that has breached the perimeter and is untrusted, and you can have a trusted employee working from a coffee shop that is unable to access company resources. 

The perimeter security model work effectively when all employees work exclusively in buildings owned by the enterprise, but doesn't work nearly as well when a workforce is mobile. 

> Unlike the traditional perimeter security model, BeyondCorp dispels the notion of network segmentation as the primary mechanism for protecting sensitive resources. Instead, all applications are deployed to the public Internet, accessible through a user and device-centric authentication and authorization workflow.

ScaleFT put together [a website](https://www.beyondcorp.com/) that has a more detailed explanation of the BeyondCorp model.

## Implementation 

While you could technically implement the BeyondCorp model on your own, the architecture requires you to build some non-trivial infrastructure (see image). [This](https://www.scaleft.com/blog/beyondcorp-outside-of-google/) blog post by ScaleFT goes into some great deal on the components needed to build a BeyondCorp on your own. 

![](http://www.noqcks.io/img/beyondcorp-model.png)

For most it will be more cost-effective to leverage a BeyondCorp service provider. The following companies provide some type of BeyondCorp services.

- [ScaleFT/Okta](https://www.scaleft.com/): Recently acquired by Okta, ScaleFT provides a similar setup to Pritunl Zero w/ client certificate architecture to connect to servers. 
- [Pritunl Zero](https://zero.pritunl.com/): An open-source BeyondCorp offering from the great Zachary Huff of [Pritunl](https://pritunl.com/). 
- [Duo Beyond](https://duo.com/pricing/duo-beyond)
- [Google](https://cloud.google.com/beyondcorp/): BeyondCorp is now available as a Google Cloud solution called context-aware access that is powered by Cloud Identity, Identity-Aware Proxy, Identity & Access Management, and VPC Service Controls. 
- [PrivX](https://www.ssh.com/products/privx): PrivX by [ssh.com](https://www.ssh.com) is Just-In-Time access management, adds traceability to shared accounts using shared passwords, and conveniently combines access management for your On-Prem, AWS, Azure and GCP infrastructure, all in one multi-cloud solution.

If you are aware of any more companies, please submit a PR.

For a review of their BeyondCorp migration and advice on how to implement your own, take a look at [this](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/f29b3e764b1122d508b7b53544a3bbadd6cd1101.pdf) paper by Google.

## Resources 
- [BeyondCorp website](https://www.beyondcorp.com/) by ScaleFT
- [BeyondCorp: How Google Ditched VPNs for Remote Employee Access](https://thenewstack.io/beyondcorp-google-ditched-virtual-private-networking-internal-applications/)
- [The paper that started Zero Trust](https://www.nist.gov/sites/default/files/documents/2017/06/05/040813_forrester_research.pdf)


---
¹ "Never Trust, Always Verify" - all network traffic is untrusted. There is no "trusted" traffic. This model was put forward by [John Kindervag in 2010](https://www.nist.gov/sites/default/files/documents/2017/06/05/040813_forrester_research.pdf).
