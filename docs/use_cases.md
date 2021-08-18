# Use cases

<span class="subtitle">

These are some of the use cases for SLSA.  Of these the first use case (a developer checking
their own packages prior to publishing) is the most ready for adoption as it does not require
interactions with any other party.

</span>

<table class="link-tree">
<th>On this page</th>
<tr>
<td>

[Developer publishing a software package](#developer-publishing-a-software-package)

</td>
</tr>
<tr>
<td>

[Software consumer using third party software](#software-consumer-using-third-party-software)

</td>
</tr>
<tr>
<td>

[Package repository accepting a package](#package-repository-accepting-a-software-package)

</td>
</tr>
<tr>
<td>

[Checking an artifact’s SLSA level](#checking-an-artifacts-slsa-level)

</td>
</tr>
<tr>
<td>

[Determining a package’s intent](#determining-a-packages-intent)

</td>
</tr>
<td>

[IN DEVELOPMENT]: Automatically verifying software
</td>
</tr>

</table>

<table class="link-tree">
<th>Further reading</th>
<tr>
<td>

[Example of use](/example.md)

</td>
</tr>
<tr>
<td>

[Case studies](https://github.com/slsa-framework/slsa/tree/main/case-studies)

</td>
</tr>

</table>

## Developer publishing a software package

### How an organisation can protect their users from malicious damage to the software they publish

| Subject   | Description                              |
|:----------|:-----------------------------------------|
| **Users** | Developers                               |
| **Goals** | Protecting users from malicious changes  |
|           | Protecting their company’s reputation    |
|           | Access to metadata for auditing/analysis |

A software development organisation (e.g. BarInc) wants to protect consumers of their software from malicious changes to the BarImage container image they publish. They also want to prevent any negative consequences and  damage to their reputation which would occur if that happened, and to have access to metadata for auditing and ad hoc analysis.

### How to do it

BarInc can achieve these goals when publishing the container image by:

-   Upgrading their source control systems to meet higher SLSA levels
-   Upgrading their build system to meet higher SLSA levels
-   Ensuring BarImage must go through a secure control-point in order to be published
-   Having the control-point check the candidate BarImage against its provenance, checking that:
    -   The expected builder created it
    -   The builder meets a minimum SLSA level
    -   The source repositories listed in the provenance meets a minimum SLSA level
    -   The build entry point listed in the provenance is expected
    -   The binary dependencies listed in the provenance meets a minimum SLSA level
-   Only publishing the container image if all the above checks pass
-   Storing the provenance and all other attestations for future reference

### Limitations

This approach doesn’t protect their users from a published BarImage being tampered with after production. There may be other ways to address these concerns such as code signing after verification, time-of-use verification, or encouraging use of the SLSA framework by their software consumers.

## Software consumer using third party software

A developer using BarImage wants to ensure it hasn't been tampered with before using it.

They could do this by:

1.  Requesting BarInc to publish the [in-toto SLSA Provenance] and any additional attestations (such
    as [source control attestations]) for BarImage each time it is released.
2.  Requesting BarInc to publish the public keys its builder uses to sign the attestations.
    -   (TBD) [Determine how to convey these keys].
3.  Requesting BarInc to confirm what SLSA level their builder and source control system meet.
    -   In the future there may be an accredidation body that confirm this _for_ BarInc.
4.  Determining what policy to apply to BarImages.
    -   They could create this policy on first use based on the data provided in the in-toto SLSA Provenance.
        Any significant deviations (e.g. builder changed, source repo changed) would cause failure. OR
    -   BarInc could _publish_ a suggested policy for users of BarImage on their website.
5.  Establishing a secure control-point that any uses of BarImage must pass through in order to be used.
    -   E.g. On import to a local Docker registry.
6.  Having the control-point check the candidate BarImage against its provenance, checking it against the
    policy from #4.
7.  Only importing the container image if all the checks in #6 pass.

This approach protects the developer without having to rely on any trust in intermediate package
repositories.

## Package Repository accepting a software package

A Package Repository (e.g. Docker Hub) wants to protect their users from malicious changes to the
container images uploaded to the repo.

They could do this by:

1.  Requesting publishers of containers to publish the [in-toto SLSA Provenance] and any additional
    attestations (such as [source control attestations]) each time a new image is pushed to the
    repository.
    -   (TBD) Where to store this provenance?
2.  Requesting publishers to publish the public keys it's builder uses to sign the attestations.
    -   (TBD) [Determine how to convey these keys]
3.  Requesting publishers to confirm what SLSA level their builder and source control system meet.
    -   In the future there may be an accredidation body that confirm this _for_ the publishers.
4.  Determining what policy to apply to published images.
    -   They could create this policy on first use based on the data provided in the in-toto SLSA Provenance.
        Any significant deviations (e.g. builder changed, source repo changed) would cause a push
        failure. OR
    -   The Package Repository could have publishers configure their specific policy as a part of their
        repo.
        -   The Package Repository could make these policies publicly readable by users of the repo.
        -   (TBD) How to securely update these policies.
5.  Checking new containers against the policy from #4.
6.  Preventing container images that fail the check in #5 from being made public.

This approach could protect users of protected repos from malicious tampering without requring all
users to do their own policy checks of each image they consume.

## Checking an artifact’s SLSA level

## Determining a package's intent

[Determine how to convey these keys]: https://github.com/slsa-framework/slsa/issues/101
[in-toto SLSA Provenance]: https://slsa.dev/provenance
[source control attestations]: https://github.com/in-toto/attestation/issues/47
