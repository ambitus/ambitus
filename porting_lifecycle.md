# Lifecycle for ports of open source software

This document outlines the proposed lifecycle for a port which is managed by Ambitus. Every port managed by Ambitus has a stage it is in, with the expectation of ports needing to complete the graduation requirements of that stage to move on to the next stage. Ports receive of all maturities have access to all resources of Ambitus, but if there is contention more mature projects will generally have priority.

## Incubation

To be accepted to the Incubation Stage, a port must complete the [proposal process](port_proposal.md).

Every 12 months, each Incubation Stage port will come to a vote with the TSC. A supermajority vote is required to renew a port at Incubation Stage for another 12 months or move it to active stage. If there is not a supermajority for any of these options, the port is not renewed.

## Active

To graduate from Incubation Stage, or for a new project to join as an Active Stage port, a port must complete the [proposal process](port_proposal.md) plus:

* Have a working build and build environment ( to donate to the upstream project upon graduation to Upstreamed stage )
* Have attempted to achieve a Core Infrastructure Initiative [Best Practices Badge](https://bestpractices.coreinfrastructure.org/) for the project, or if the project currently has one ensure that it is operating by the stated declarations in it's application.
* Have maintained a fork in-sync with the latest release of the upstream project.
* Have a public list of adopters of the ported software (e.g., ADOPTERS.md).
* Complete a code licensing scan to ensure licensing is inline with the upstream project's guidelines.
* Have at least 2 individuals able to maintain the port.
* Receive a supermajority vote from the TSC to move to Active stage.

Projects start at the Active Stage if they can demonstrate sufficient maturity. Projects can remain in an Incubation Stage indefinitely, but they are normally expected to move to Active Stage within two years.

## Upstreamed

A project is considered 'upstreamed' if the modifications made to the project to support the mainframe architecture are accepted and included in a release. Any CI or build infrastructure used will be donated to the upstream to maintain compatibility. The appointed maintainers will also stay involved in the project; if at any time a maintainer is unable to remain involved then the Ambitus TSC may appoint a new maintainer subject the upstream project's governance policies.
