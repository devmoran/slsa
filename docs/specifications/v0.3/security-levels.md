---
title: Security Levels
order: 1
version: 0.2
layout: specifications
hero_text: SLSA’s levels prioritize measures to provide you and your users with appropriate, industry-recognized security guarantees. They make it easier to know what’s most relevant to an immediate scenario, and that over time, there’s more integrity built in to the systems you’re working with.<br><br>Each of the levels build upon baseline guarantees that the source code you analyze and trust is the code that you're actually using, starting by prioritizing the security of packages you’re using, and then focusing effort to securing the infrastructure in place to deliver that package.<br><br>For something to be compliant with a SLSA level, that shows a reasonable, agreed upon level of security. It shows that the measures to harden integrity have progressed from foundational efforts to a more secure software supply chain overall, and can help allow users to automatically verify artifacts, influence policy and protect against more advanced threats. 
description: Start here for the level breakdowns
---

<span class="subtitle">

Each level provides an increasing degree of confidence, a way to say that software hasn’t been tampered with and can be securely traced back to its source.

</span>

| Level | Description                                   | Example                                               |
| :---- | :-------------------------------------------- | :---------------------------------------------------- |
| 1     | Documentation of the build process            | Unsigned provenance                                   |
| 2     | Tamper resistance of the build service        | Hosted source/build, signed provenance                |
| 3     | Extra resistance to specific threats          | Security controls on host, non-falsifiable provenance |
| 4     | Highest levels of confidence and trust        | Two-party review + hermetic builds                    |

It can take years to achieve the ideal security state - intermediate milestones are important. SLSA guides you through gradually improving the security of your software. Artifacts used in critical infrastructure or vital business operations may want to attain a higher level of security, whereas software that poses a low risk can stop when they're comfortable.

## Detailed explanation

| Level | Requirements |
| ----- | ------------ |
| 0     | **No guarantees.** SLSA 0 represents the lack of any SLSA level. |
| 1     | **The build process must be fully scripted/automated and generate provenance.** Provenance is metadata about how an artifact was built, including the build process, top-level source, and dependencies. Knowing the provenance allows software consumers to make risk-based security decisions. Provenance at SLSA 1 does not protect against tampering, but it offers a basic level of code source identification and can aid in vulnerability management. |
| 2     | **Requires using version control and a hosted build service that generates authenticated provenance.** These additional requirements give the software consumer greater confidence in the origin of the software. At this level, the provenance prevents tampering to the extent that the build service is trusted. SLSA 2 also provides an easy upgrade path to SLSA 3. |
| 3     | **The source and build platforms meet specific standards to guarantee the auditability of the source and the integrity of the provenance respectively.** We envision an accreditation process whereby auditors certify that platforms meet the requirements, which consumers can then rely on. SLSA 3 provides much stronger protections against tampering than earlier levels by preventing specific classes of threats, such as cross-build contamination. |
| 4     | **Requires two-person review of all changes and a hermetic, reproducible build process.** Two-person review is an industry best practice for catching mistakes and deterring bad behavior. Hermetic builds guarantee that the provenance’s list of dependencies is complete. Reproducible builds, though not strictly required, provide many auditability and reliability benefits. Overall, SLSA 4 gives the consumer a high degree of confidence that the software has not been tampered with. |

The SLSA level is not transitive ([see our FAQs](faq.md)). This makes each artifact’s SLSA rating independent from one another, allowing parallel progress and prioritization based on risk. The level describes the integrity protections of an artifact’s build process and top-level source, but nothing about the artifact’s dependencies. Dependencies have their own SLSA ratings, and it is possible for a SLSA 4 artifact to be built from SLSA 0 dependencies.

## Level requirements

The following table provides a summary of the [requirements](requirements.md) for each level.

| Requirement                          | SLSA 1 | SLSA 2 | SLSA 3 | SLSA 4 |
| ------------------------------------ | ------ | ------ | ------ | ------ |
| Source - [Version controlled]        |        | ✓      | ✓      | ✓      |
| Source - [Verified history]          |        |        | ✓      | ✓      |
| Source - [Retained indefinitely]     |        |        | 18 mo. | ✓      |
| Source - [Two-person reviewed]       |        |        |        | ✓      |
| Build - [Scripted build]             | ✓      | ✓      | ✓      | ✓      |
| Build - [Build service]              |        | ✓      | ✓      | ✓      |
| Build - [Build as code]              |        |        | ✓      | ✓      |
| Build - [Ephemeral environment]      |        |        | ✓      | ✓      |
| Build - [Isolated]                   |        |        | ✓      | ✓      |
| Build - [Parameterless]              |        |        |        | ✓      |
| Build - [Hermetic]                   |        |        |        | ✓      |
| Build - [Reproducible]               |        |        |        | ○      |
| Provenance - [Available]             | ✓      | ✓      | ✓      | ✓      |
| Provenance - [Authenticated]         |        | ✓      | ✓      | ✓      |
| Provenance - [Service generated]     |        | ✓      | ✓      | ✓      |
| Provenance - [Non-falsifiable]       |        |        | ✓      | ✓      |
| Provenance - [Dependencies complete] |        |        |        | ✓      |
| Common - [Security]                  |        |        |        | ✓      |
| Common - [Access]                    |        |        |        | ✓      |
| Common - [Superusers]                |        |        |        | ✓      |

<!-- markdownlint-disable-next-line MD036 -->
_○ = required unless there is a justification_

[access]: requirements.md#access
[authenticated]: requirements.md#authenticated
[available]: requirements.md#available
[build as code]: requirements.md#build-as-code
[build service]: requirements.md#build-service
[dependencies complete]: requirements.md#dependencies-complete
[ephemeral environment]: requirements.md#ephemeral-environment
[hermetic]: requirements.md#hermetic
[isolated]: requirements.md#isolated
[non-falsifiable]: requirements.md#non-falsifiable
[parameterless]: requirements.md#parameterless
[reproducible]: requirements.md#reproducible
[retained indefinitely]: requirements.md#retained-indefinitely
[scripted build]: requirements.md#scripted-build
[security]: requirements.md#security
[service generated]: requirements.md#service-generated
[superusers]: requirements.md#superusers
[two-person reviewed]: requirements.md#two-person-reviewed
[verified history]: requirements.md#verified-history
[version controlled]: requirements.md#version-controlled

## <a name="threats"></a>Supply chain threats

Attacks can occur at every link in a typical software supply chain, and these kinds of attacks are increasingly public, disruptive and costly in today’s environment. In developing SLSA, the requirements for each level are designed to specifically mitigate the risk of such known examples. For a much deeper technical analysis of the risks and how SLSA mitigates them, see [Threats and mitigations](threats.md).

![Supply Chain Threats](images/supply-chain-threats.svg)

Many recent high-profile attacks were consequences of supply-chain integrity vulnerabilities, and could have been prevented by SLSA's framework. For example:

|     | Threat                                                                | Known example                                                                                                                                                                                  | How SLSA can help                                                                                                                                                                                                                     |
| --- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A   | Submit bad code to the source repository                              | [Linux hypocrite commits]: Researcher attempted to intentionally introduce vulnerabilities into the Linux kernel via patches on the mailing list.                                              | Two-person review caught most, but not all, of the vulnerabilities.                                                                                                                                                                   |
| B   | Compromise source control platform                                    | [PHP]: Attacker compromised PHP's self-hosted git server and injected two malicious commits.                                                                                                   | A better-protected source code platform would have been a much harder target for the attackers.                                                                                                                                       |
| C   | Build with official process but from code not matching source control | [Webmin]: Attacker modified the build infrastructure to use source files not matching source control.                                                                                          | A SLSA-compliant build server would have produced provenance identifying the actual sources used, allowing consumers to detect such tampering.                                                                                        |
| D   | Compromise build platform                                             | [SolarWinds]: Attacker compromised the build platform and installed an implant that injected malicious behavior during each build.                                                             | Higher SLSA levels require [stronger security controls for the build platform](requirements.md#build-requirements), making it more difficult to compromise and gain persistence.                                                      |
| E   | Use bad dependency (i.e. A-H, recursively)                            | [event-stream]: Attacker added an innocuous dependency and then later updated the dependency to add malicious behavior. The update did not match the code submitted to GitHub (i.e. attack F). | Applying SLSA recursively to all dependencies would have prevented this particular vector, because the provenance would have indicated that it either wasn't built from a proper builder or that the source did not come from GitHub. |
| F   | Upload an artifact that was not built by the CI/CD system             | [CodeCov]: Attacker used leaked credentials to upload a malicious artifact to a GCS bucket, from which users download directly.                                                                | Provenance of the artifact in the GCS bucket would have shown that the artifact was not built in the expected manner from the expected source repo.                                                                                   |
| G   | Compromise package repository                                         | [Attacks on Package Mirrors]: Researcher ran mirrors for several popular package repositories, which could have been used to serve malicious packages.                                         | Similar to above (F), provenance of the malicious artifacts would have shown that they were not built as expected or from the expected source repo.                                                                                   |
| H   | Trick consumer into using bad package                                 | [Browserify typosquatting]: Attacker uploaded a malicious package with a similar name as the original.                                                                                         | SLSA does not directly address this threat, but provenance linking back to source control can enable and enhance other solutions.                                                                                                     |

[linux hypocrite commits]: https://lore.kernel.org/lkml/202105051005.49BFABCE@keescook/
[php]: https://news-web.php.net/php.internals/113838
[webmin]: https://www.webmin.com/exploit.html
[solarwinds]: https://www.crowdstrike.com/blog/sunspot-malware-technical-analysis/
[event-stream]: https://schneider.dev/blog/event-stream-vulnerability-explained/
[codecov]: https://about.codecov.io/apr-2021-post-mortem/
[attacks on package mirrors]: https://theupdateframework.io/papers/attacks-on-package-managers-ccs2008.pdf
[browserify typosquatting]: https://blog.sonatype.com/damaging-linux-mac-malware-bundled-within-browserify-npm-brandjack-attempt

A SLSA level helps give consumers confidence that software has not been tampered with
and can be securely traced back to source—something that is difficult, if not
impossible, to do with most software today.

## Limitations

SLSA can help reduce supply chain threats in a software artifact, but there are limitations.

-   There are a significant number of dependencies in the supply chain for mant artifacts. The full graph of dependencies could be intractably large.
-   In practice, a team working on security will need to identify and focus on the important components in a supply chain. This can be performed manually, but the effort could be significant.
-   An artifact’s SLSA level is not transitive ([see our FAQs](faq.md)) and dependencies have their own SLSA ratings. This means that it is possible for a SLSA 4 artifact to be built from SLSA 0 dependencies. So, while the main artifact has strong security, risks may still exist elsewhere. The aggregate of these risks will help software consumers understand how and where to use the SLSA 4 artifact.
-   While automation of these tasks will help, it isn’t practical for every software consumer to fully vet the entire graph of every artifact. To close this gap, auditors and accreditation bodies could verify and assert that something meets the SLSA requirements. This could be particularly valuable for closed source software.

As part of our [roadmap](roadmap.md), we’ll explore how to identify important components, how to determine aggregate risk throughout a supply chain, and the role of accreditation.
