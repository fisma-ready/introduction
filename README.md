# Introduction

In the United States, all Federal Government information systems are regulated by the [Federal Information Security Management Act](http://en.wikipedia.org/wiki/Federal_Information_Security_Management_Act_of_2002) (FISMA). This law empowers the [National Institute for Standards and Technology](http://www.nist.gov/) (NIST) to issue guidance on what security controls should exist on information systems, especially those in production.

While nothing is completely without risk, federal agencies require systems to receive an Authority to Operate (ATO) before putting a system into production. An ATO is the final step in NIST's [risk management framework](http://csrc.nist.gov/groups/SMA/fisma/framework.html). An ATO represents the agency's acceptance of the risk presented in operating the system, after all due diligence has been completed and reasonable controls put in place. It usually takes the form of a signed letter from a high-level agency executive, who serves as the Authorizing Official (AO).

[NIST Special Publication (SP) 800-53 Revision 4](http://csrc.nist.gov/groups/SMA/fisma/controls.html) lists various control baselines - groupings of both technical and organizational security controls. These control baselines change depending on how the system has been [categorized](http://csrc.nist.gov/groups/SMA/fisma/categorization.html). Implementing, documenting, and assessing these controls on a system of even moderate complexity can be incredibly time consuming and prone to error.

[18F](https://18F.gsa.gov), a digital services delivery team within the [General Services Administration](http://www.gsa.gov) (GSA), is invested in making this process more efficient and effective, while radically reducing the time necessary to get an ATO. One way to increase both quality and speed is to heavily reuse pre-approved components in the system.

## A community project

**FISMA Ready** is a community run project. While 18F is investing resources into starting the community, the intention is to run FISMA Ready via open and collaborative principles, with a diverse group of contributors participating and leading the way forward. We'll soon be posting more about our outreach initiatives and how we intend to moderate and manage the community. Keep an eye on the [18F news feed](https://18f.gsa.gov/news/) for official updates.

If you're looking for systems and components that have received a full cybersecurity assessment by a third-party, GSA provides the [FedRAMP program](http://cloud.cio.gov/fedramp) and a [list of cloud service providers that have achieved an authorization](http://cloud.cio.gov/fedramp/cloud-systems).

## Security, not obscurity

We believe that our systems will be safer if we work in the open. It's a simple mathematical reality that there will always be more security expertise outside of our team than within it. The only way to stay ahead of 21st century threats is to utilize the greatest amount of talent possible via transparent collaboration. Obscurity is the weakest of all security controls and must always be considered in a context of net security trade-offs. Our _overall_ security is greatly increased by working with the community to discover unknown flaws and creative improvements. 

## Considerations and prerequisites

Before starting to use FISMA Ready components, implement the following best practices.

### Secure your cloud infrastructure

This work presumes the system is deployed on cloud infrastructure that has a [FedRAMP](http://cloud.cio.gov/fedramp) authorization.

FedRAMP pre-approves cloud infrastructure as meeting NIST controls. Many of the NIST controls assumed the agency still has physical control to the servers, or hypervisor level access.

Increasingly, these controls are instead implemented by [vendors providing Infrastructure as a Service (IaaS)](http://cloud.cio.gov/fedramp/cloud-systems). FedRAMP, along with an accredited third-party assessor, ensures the vendor's controls meet federal guidelines. An example of a FedRAMP control can be found in NIST 800-53 under _PE-2 (2): Physical Access Authorizations - Two Forms of Identification_. In a cloud environment, the agency cannot access the physical servers, so this control must be implemented by the vendor.

### Continuous monitoring and a team where everyone is responsible

Using FedRAMP, or pre-approved system components in general, does not remove the need to implement a program of continuous monitoring or other intrusion detection systems. If using a true IaaS solution, federal technology teams are responsible for a continuous monitoring program.

The vast majority of a system's security comes not from technical controls, but the culture of the team responsible for the system. In order to bridge the gaps between application developers, system administrators and engineers, and cybersecurity professionals, federal agencies should consider re-organizing their technology teams under a [DevOps model](http://en.wikipedia.org/wiki/DevOps).

On a DevOps team, no one gets to throw work "over the wall" where it becomes some other team's problem. Everyone is responsible for success, and metrics should align incentives. One team doesn't get to declare victory because their portion of the work is done. Until the system is shipped - secure and performant in production - everyone is still on the hook.

### Trust but verify

If an agency reuses a system component that has received an ATO from another agency, they should be sure to test the security controls are indeed in place. Creators and maintainers of FISMA Ready components should release comprehensive test suites to ensure this process is both accurate and quick.

Once an initial re-assessment has been completed, agencies should consider the use of hashes on the virtual machine, container, or package to ensure they are always building from a known component state.

## Infrastructure as Code

We believe anyone should be able to quickly re-engineer a secure component, without having to rely on a golden master image from 18F or any other federal technology team. To that end, we'll represent Infrastructure as Code (IaC) wherever possible. We're really excited to work with the community to create a thriving ecosystem in this space, without any major vendor or framework lock-ins.

## Free to use

FISMA Ready work must be committed to the public domain.

This only applies to the work created by 18F. Licenses on technical reference documents or on the software components themselves may apply. 18F **strongly** urges FISMA Ready contributors to submit their cybersecurity work into the public domain. Managing multiple licenses, even if they're open source licenses, will slow adoption amongst the Federal community. 18F believes developers and consultants who work on or around open software should compete on quality, feature set, speed, and cybersecurity *assurance* - not cybersecurity *compliance*.

## Future changes

This is a living document. 18F expects to make frequent changes to this policy as it develops, and we welcome pull requests.
