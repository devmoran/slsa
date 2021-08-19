# Use cases

## Consuming third party software

A software development organisation developer (e.g. FooCo) using third party software (e.g. HowDo developed by HowInc) wants to ensure it hasn’t been tampered with before using it. They could take the following steps to check, protecting the organisation from the software they consume without having to rely on any trust in intermediate package repositories.

| Subject   | Description                   |
|:----------|:------------------------------|
| **Users** | Software consumers            |
| **Goals** | Protecting against tampering  |

### How to do it

-   Requesting HowInc publish the in-toto SLSA provenance and any additional attestations (e.g. source control attestations) for HowDo each time it’s released
-   Requesting HowInc publish the public keys its builder uses to sign the attestations
    -   Determine how to convey these keys
-   Requesting HowInc confirm what SLSA level their builder and source control system meet
-   Determining what policy to apply to HowDo
    -   This policy could be created on first use based on the data in the in-toto SLSA provenance. Any significant deviations (e.g. the builder or source repository changed) would cause failure
    -   Or HowInc could publish a suggested policy for HowDo users on their website
-   Establishing a secure control-point that any HowDo users must pass through to be used
    -   e.g. on import to a local Docker registory
-   Having the control-point check the candidate HowDo against its provenance, checking it -   against the policy mentioned above
-   Only importing the siftware artifact if all the above checks pass

### Limitations

This use case relies on FooCo trusting the SLSA information that HowInc provides. In the future, there may be accreditation bodies that confirm this information.
