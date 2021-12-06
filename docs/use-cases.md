---
title: Use Cases
layout: standard
subheading: Safeguarding artifact integrity across any supply chain
hero_text: Here’s what SLSA looks like in practice, typical cases to explore and break down how compliance can provide protection. Whether you’re a developer working on a project or part of an enterprise, SLSA can be helpful both for securing your supply chain and clarifying existing tools and processes.
order: 0
---
<!--{% if false %}-->

**NOTE: This site is best viewed at https://slsa.dev.**

<!--{% endif %}-->

<section class="section bg-pastel-green flex justify-center items-center">
    <div class="wrapper inner w-full">
        <div class="flex justify-between items-start mb-16">
            <div class="text w-1/3">
<div class="h3 p-0">

### Example use cases

</div>
            </div>
            <div class="w-2/4">
            </div>
        </div>
        <div class="flex justify-between items-start mb-12 rounded-xl p-10 bg-white">
            <div class="text w-2/3">
                <h3 class="h4 p-0">Developers and SLSA</h3>
            </div>
            <div class="w-3/4">
                    <p>
                        To inventory all the source and build systems (Level 1)
Decoupling development toolchains (e.g. untrusted IDE extensions) and workflows from the artifacts you publish (Level 2)
Providing a public audit trail of source and builds to demonstrate a commitment to securing a supply chain (Level 3)
Eliminating unilateral access to produce releases so that compromise of your machine or credentials alone won’t be enough to backdoor your package (Level 4)
                    </p>
            </div>
        </div>
        <div class="flex justify-between items-start mb-12 rounded-xl p-10 bg-white">
            <div class="text w-2/3">
                <h3 class="h4 p-0">Enterprises and SLSA</h3>
            </div>
            <div class="w-3/4">
                    <p>
                    Accounting for all build processes and systems used (Level 1)
Ensuring that release artifacts are built through a common, publicly accessible workflow to facilitate onboarding new maintainers and providing transparency to your users (Level 2)
Stratifying applications by their security sensitivity and ensuring low-assurance projects can’t adversely impact higher-assurance ones (Level 3)
Preventing the compromise of a single employee leading to compromise all your users (Level 4)
                    </p>
            </div>
        </div>
        <div class="flex justify-between items-start mb-12 rounded-xl p-10 bg-white">
            <div class="text w-2/3">
                <h3 class="h4 p-0">Platforms and SLSA</h3>
            </div>
            <div class="w-3/4">
                    <p>
                    Recording the steps necessary to build a release (Level 1)
Establishing a cryptographic chain of custody between trusted builds and your release and code-signing workflows (Level 2)
                    </p>
            </div>
        </div>
    </div>
</section>

<section class="section bg-white flex justify-center items-center">
    <div class="wrapper inner w-full">
        <div class="flex justify-between items-start mb-16">
            <div class="text w-2/3">
<div class="h3 p-0 mb-8">

### Case Studies

</div>
<p>These case studies go much more in depth. Starting from a particular scenario, they look at how you might harden an entire system over time, starting with immediate problems to solve and following through next steps to incrementally progress through to the higher SLSA levels, with space for the development of automatic analysis and policies. </p>
            </div>
            <div class="w-2/4">
            </div>
        </div>
        <p class="h4">Example case studies</p>
        <ul class="mt-6 mb-6">
            <li>
                <a class="p-0 m-0 text-green-dark w-full hover:no-underline" href="/ }}">
                    <p class="h4 font-normal flex items-center pt-8 ">
                        <span class="mr-4">
                        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0.896251 18C-0.298751 12.0505 -0.298752 5.94951 0.896249 -7.47629e-07C7.1285 2.02552 12.9429 5.081 18 9C12.9429 12.919 7.1285 15.9745 0.896251 18Z" fill="#40DB88"/></svg></span>
                        Publishing a software package
                    </p>
                </a>
            </li>
            <li>
                <a class="p-0 m-0 text-green-dark border-t border-black-900 w-full hover:no-underline" href="/ }}">
                    <p class="h4 font-normal flex items-center pt-8 ">
                        <span class="mr-4">
                        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0.896251 18C-0.298751 12.0505 -0.298752 5.94951 0.896249 -7.47629e-07C7.1285 2.02552 12.9429 5.081 18 9C12.9429 12.919 7.1285 15.9745 0.896251 18Z" fill="#40DB88"/></svg></span>
                        Consuming third party software
                    </p>
                </a>
            </li>
            <li>
                <a class="p-0 m-0 text-green-dark border-t border-black-900 w-full hover:no-underline" href="/ }}">
                    <p class="h4 font-normal flex items-center pt-8">
                        <span class="mr-4">
                        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0.896251 18C-0.298751 12.0505 -0.298752 5.94951 0.896249 -7.47629e-07C7.1285 2.02552 12.9429 5.081 18 9C12.9429 12.919 7.1285 15.9745 0.896251 18Z" fill="#40DB88"/></svg></span>
                        Package repository accepting a software package
                    </p>
                </a>
            </li>
            <li>
                <a class="p-0 m-0 text-green-dark border-t border-black-900 w-full hover:no-underline" href="/ }}">
                    <p class="h4 font-normal flex items-center pt-8 pb-8">
                        <span class="mr-4">
                        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0.896251 18C-0.298751 12.0505 -0.298752 5.94951 0.896249 -7.47629e-07C7.1285 2.02552 12.9429 5.081 18 9C12.9429 12.919 7.1285 15.9745 0.896251 18Z" fill="#40DB88"/></svg></span>
                        Incrementally reaching Level 4 using curl
                    </p>
                </a>
            </li>
        </ul>
        <div class="bg-pastel-green h-full rounded-lg p-10"> 
            <p class="h4 mb-6 font-bold">Real world examples</p>
            <p><strong>If you’ve been using SLSA already, get in touch.</strong><br><br>
The scenarios above are proof of concepts and theoretical explorations. As more people adopt SLSA, we’ll add case studies to walk you through what long term adoption of the SLSA framework could look like, with real world scenarios, application and discovery, planning and strategic development.<br><br> 
The contribution guidelines help guide your feedback, and every contribution is useful for others to see how SLSA can be used in their project or organization.</p>
            <a target="_blank" href="https://github.com/slsa-framework/slsa/blob/main/CONTRIBUTING.md" class="cta-link mt-8">Submit a case study</a>
        </div>
    </div>  
</section>



<!-- # Use cases

<span class="subtitle">

The following are some typical cases to explore how SLSA compliance can provide protection. In each, we’ve detailed goals that users need to meet, how organizations can use the SLSA framework to help meet them, and limitations that might be faced.

</span>
<div class="link-tree use-cases">

|                                                                                                                                                                                                                   |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Publishing a software package](/publishing-a-software-package.md) How a developer can protect their users from malicious changes to the software they publish                                                    |
| [Consuming third party software](/consuming-third-party-software.md) How a developer can work with third party software suppliers to reduce risk in a supply chain                                                |
| [Package repository accepting a package](/package-repository-accepting-a-software-package.md) How a repository can protect their users from malicious changes to software artifacts published in their repository |
| [IN DEVELOPMENT]: Checking an artifact’s SLSA level                                                                                                                                                               |
| [IN DEVELOPMENT]: Determining a package’s intent                                                                                                                                                                  |
| [IN DEVELOPMENT]: Automatically verifying software                                                                                                                                                                |

</div>

For a [full example](../example.md) that explores edge cases in greater detail, we created a use case for using curl through its official docker image.

[Want to contribute?](https://github.com/slsa-framework/slsa/tree/main/case-studies) These are only a few of the most common use cases for developers, software consumers and repository maintainers. We welcome any real life scenarios you’ve faced using SLSA in your projects. -->