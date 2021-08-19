# Use cases

## Publishing a software package

A software development organisation (e.g. BarInc) wants to protect consumers of their software from malicious changes to the BarImage container image they publish. They also want to prevent any negative consequences and  damage to their reputation which would occur if that happened, and to have access to metadata for auditing and ad hoc analysis.

| Subject   | Description                              |
|:----------|:-----------------------------------------|
| **Users** | Developers                               |
| **Goals** | Protecting users from malicious changes  |
|           | Protecting their company’s reputation    |
|           | Access to metadata for auditing/analysis |

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

<p>&nbsp;</p>
<table class="link-tree">
<th>Use cases</th>
<tr>
<td>

[Publishing a software package](/publishing-a-software-package.md)

</td>
</tr>
<tr>
<td>

[Consuming third party software](/consuming-third-party-software.md)

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
