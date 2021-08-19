# Use cases

## Package Repository accepting a software package

A Package Repository (e.g. Docker Hub) wants to protect their users from malicious changes to the container images uploaded to the repo.

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
