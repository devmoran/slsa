---
title: Get started
layout: standard
subheading: Safeguarding artifact integrity across any supply chain
hero_text: If you’re looking to jump straight in and try SLSA, here’s a quick start guide for the steps to take to reach the first SLSA level. Level 1 ensures that you’re setting up the foundation of trust in a system and that all your applications are generating appropriate provenance data. It also sets a baseline to achieve higher SLSA compliance later, which we explain in detail below.
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

### Reaching SLSA Level 1

#### Effort: Low

</div>
            </div>
            <div class="w-2/4">
                <div class="bg-white h-full rounded-lg p-10">
                    <p class="h5 font-bold mb-6">Overview<p>
                    <p>
                        This guide will help you achieve Level 1, and it should take less than a couple of hours for an individual project. By following the steps, you’ll soon be compliant with these SLSA requirements:
<ul class="list-disc my-6 pl-6"><li>Producing provenance data</li>
<li >Automating your builds</li></ul>
                    </p>
                    <p class="h5 font-bold mb-6">Steps</p>
                    <ul class="list-decimal mt-6 mb-6 pl-6">
                        <li>Read the Level 1 <a href="/specifications/{{site.current_version}}/requirements#build-requirements">build</a> and <a href="/specifications/{{site.current_version}}/requirements#provenance-requirements">provenance</a> requirements</li>
                        <li>Choose a compliant version control system (if needed)</li>
                        <li>Choose a scripted build tool (if needed)</li>
                        <li>Create your provenance using the in-toto format (the Tools listed below can help)</li>
                        <li>Decide where you'll store the signed provenance so you and your users can easily build it into workflows</li>
                        <li>You’re Level 1! Add the SLSA Level 1 badge to your readme.</li>
                    </ul>
                    <p class="h5 font-bold mb-6">Tools</p>
                    <ul class="list-disc mt-6 pl-6">
                        <li><a href="https://github.com/slsa-framework/github-actions-demo">GitHub Actions provenance generator</a></li>
                        <li><a href="https://github.com/slsa-framework/azure-devops-demo">Azure DevOps provenance generator</a></li>
                        <li><a href="https://github.com/sigstore/cosign">Sigstore Cosign for storing signed provenance</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</section>
<section class="section bg-white flex justify-center items-center">
    <div class="wrapper inner w-full">
        <div class="flex justify-between items-start mb-16">
            <div class="text w-1/3">
<div class="h3 p-0">

### Building to higher levels

</div>
            </div>
            <div class="w-1/2">
                <div class="bg-white h-full rounded-lg">
                    <p>Once the foundations are in place with Level 1, you can start looking towards the higher levels to further strengthen artifact integrity with central monitoring, authentication and automated compilation, as well as more secure development practices. But there’s a few things to consider first:</p>
                    <div class="mt-6">
                    <p class="h4 font-normal mb-6 ">Define your ideal state</p>
                    <p class="pb-4">Which level is most realistic, which is appropriate for your project in the short term and for your immediate needs? It can take years to achieve the ideal security state, so having intermediate milestones is important.<br><br>
Not all projects require Level 4, and for others it’s impossible to achieve. If it seems unrealistic for your project, focus your efforts on Level 3 instead.</p>
</div>
<div class="mt-6">
                    <p class="h4 font-normal mb-6 ">Make progress in parallel</p>
                    <p class="pb-4">You can progressively attain higher SLSA levels. Each artifact’s SLSA level is independent from one another, allowing parallel progress and prioritization based on risk.</p>
</div>
                </div>
            </div>
        </div>
    </div>
</section>
<section class="section bg-pastel-green">
    <div class="wrapper inner w-full">
        <div class="flex flex-col justify-center items-center mb-8 w-2/3 mx-auto pl-5">
            <h4 class="h3 mb-8">Help us improve SLSA</h4>
            <div class="w-full lg:w-full mx-auto text-center">
                <p>Already at SLSA Level 1? Let us know what went well, what didn’t, and what could be improved. We’re developing new tools and onboarding resources to make the process even easier, so your contribution really goes a long way.</p>
                <a href="https://github.com/slsa-framework/slsa/issues" class="cta-link center mt-8">Leave a GitHub issue</a><br>
                <a href="community" class="cta-link center mt-8">Join the community</a>
            </div>
        </div>
    </div>
</section>
