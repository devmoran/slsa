---
title: Introduction
layout: landing
subheading: Safeguarding artifact integrity across any supply chain
hero_text: SLSA is a set of standards and technical controls you can adopt to improve artifact integrity, and build towards completely resilient systems. It’s not a single tool, but a step-by-step outline to prevent artifacts being tampered with and tampered artifacts from being used, and at the higher levels, hardening up the platforms that make up a supply chain. These requirements are explained below, along with the rest of the essential specifications.
order: 0
version: 0.2
stages:
    - 1:
        title: Build integrity
        text: SLSA starts at the build, the last step before an artifact’s released. This makes sure software’s built from the correct sources and dependencies, and hasn’t been modified. More resilient build integrity means protection from modifying code after source control, compromised build platforms or bypassing CI/CD.
    - 2:
        title: Source integrity
        text: Requirements can then focus on the source. All source code should reflect the intent of the software producer, that code and change history stay available for investigation. More resilient source integrity means better protection from bad code submitted without review or compromised source control systems.
    - 3:
        title: Dependencies
        text: Any other software artifacts fetched during the build process. Once the earlier security checks have been put into place, applying SLSA checks recursively to any dependencies in the system can then be followed up, which helps protect potentially massive attack surfaces against  dependency confusion attacks.
levels:
    - 1:
        title: Basic security steps
        text: Level 1 means the supply chain is documented, there’s infrastructure to generate provenance, and systems are prepared for higher SLSA levels.
        badge: /images/SLSA-Badge-full-level1.svg
    - 2:
        title: After the build
        text: Level 2 shows more trustworthiness in the build, builders are source-aware, and signatures are used to prevent provenance being tampered with.
        badge: /images/SLSA-Badge-full-level2.svg
    - 3:
        title: Back to source
        text: Level 3 shows that a system’s builds are fully trustworthy, build definitions come from the source and a system has more hardened CI.
        badge: /images/SLSA-Badge-full-level3.svg
    - 4:
        title: Across the chain
        text: Level 4 means the build environment is fully accounted for, dependencies are tracked in provenance and insider threats are ruled out.
        badge: /images/SLSA-Badge-full-level4.svg
---
<!--{% if false %}-->

**NOTE: This site is best viewed at https://slsa.dev.**

<!--{% endif %}-->

<section class="section bg-white">
<!-- no indentation here to get markdown working with jekyll commonmark for styling the headings better -->
<div class="wrapper inner w-full">
<div class="mb-16">

## SLSA 101

</div>
</div>
    <div class="wrapper inner w-full">
        <div class="w-full">
<div class="h3 mb-16">

## Supply chain threats

</div>
            <p class="h3 font-semibold mb-8">
                Protecting against key threats
            </h>
        </div>
        <div class="flex flex-row justify-between items-start -ml-10 -mr-10">
            <div class="text w-1/2 pl-10">
                <p>Supply chain attacks are an ever-present threat, exploiting weakpoints to interfere with software. The SLSA framework establishes three trust boundaries encouraging the right standards, attestation and technical controls, so you can harden a system from these threats and risks.</p>
            </div>
            <div class="w-1/2 pl-10">
                <p>This means automatic capability to analyse artifacts, guarantee the original source code, protect against interference that can happen in the build and distribution processes, isolate any hidden vulnerabilities and knowing with certainty which system components might be affected.</p>
            </div>
        </div>
        <div class="my-16 w-full">
            <img class="mx-auto w-3/4" src="{{ site.baseurl }}/images/supply-chain-threats.svg" alt="supply chain full threats image" />
        </div>
    </div>
    <div class="wrapper inner w-full">
        <div class="w-full">
            <p class="h3 font-semibold mb-8">
                Real world examples
            </p>
        </div>
        <div class="flex flex-row justify-between items-start -ml-10 -mr-10">
            <div class="text w-1/2 pl-10">
                <p>High profile attacks like <strong>SolarWinds</strong>, <strong>Codecov</strong> or <strong>Linux hypocrite commits</strong> exploit the kind of supply chain integrity vulnerabilities which may go unnoticed or be underdeveloped, and quickly become extremely public, disruptive and costly in today’s environment. </p>
            </div>
            <div class="w-1/2 pl-10">
                <p>Attacks can occur at every link in a typical software supply chain, which puts an extra burden on anyone involved in complex critical systems. SLSA has been designed with these real world examples in mind to make sure they’re more common knowledge, and easier to protect against.</p>
            </div>
        </div>
    </div>
</section>
<section class="section cta_banner bg-pastel-green">
    <div class="wrapper inner w-full flex items-center justify-center">
        <a href="/specifications/{{ site.current_version}}/threats" class="cta-link">Read about threats in detail</a>
    </div>
</section>
<section class="section bg-white border-b border-black-900">
    <div class="wrapper inner w-full">
        <div class="w-full">
            <p class="h3 mb-8 font-semibold">
                How it fits into the security ecosystem
            </p>
        </div>
        <div class="flex flex-row justify-between items-start">
            <div class="text w-1/2">
                <p>There’s more to security than just protection against tampering. From vulnerability management and fuzzing to testing and developer trust, many of these require solutions where effort’s focused on the source. That’s where SLSA complements your wider security efforts, giving you confidence that the code you run is the code you analyzed.</p>
            </div>
            <div class="w-1/2">
                <img class="mx-auto" src="{{ site.baseurl }}/images/SLSA-SBOM.svg" alt="How it fits into the security ecosystem image" />
            </div>
        </div>
    </div>
</section>

<section class="section flex flex-col justify-center items-center">
<!-- no indentation here to get markdown working with jekyll commonmark for styling the headings better -->
<div class="wrapper inner w-full">
<div class="mb-16">

## Security levels

</div>
</div>
    <div class="wrapper inner w-full">
        <div class="flex justify-between items-center">
            <div class="text w-1/2">
                <h4 class="h4 mb-8 font-semibold">A ladder to the ideal state</h4>
                <p>SLSA’s requirements look at the three general main areas involved in a software artifact’s creation, and where vulnerabilities target - the build, the source, and the dependencies. As the levels scale up, they show that work’s been done to assure there’s more integrity in each area, which can be helpful in scenario planning.</p>
            </div>
            <div class="w-1/3 mx-auto">
                <img src="{{ site.baseurl }}/images/badge-exploded.svg" alt="SLSA levels badge">
            </div>
        </div>
        <div class="flex flex-wrap justify-between items-start mt-16 -ml-4 -mr-4">
          {%- for stage in page.stages -%}
            {%- assign stage_content = stage | map: stage -%}
              <div class="{% if forloop.index == 1 %}w-full{% else %}w-1/2{% endif %} pl-4 pb-4">
                <div class="bg-pastel-green rounded-lg p-10">
                    <p class="font-bold mb-4 h4">{{ stage[forloop.index].title}}</p>
                    <p>{{ stage[forloop.index].text}}</p>
                </div>
              </div>
          {%- endfor -%}
        </div>
        <div class="flex flex-col justify-between items-center mt-16">
          {%- for level in page.levels -%}
          {%- assign level_content = level | map: level -%}
              <div class="w-full {% if forloop.index != 4 %}mb-32{% endif %}">
                <article class="bg-white flex items-start justify-between">
                    <div class="w-2/4">
                        <img src="{{ site.baseurl }}{{level[forloop.index].badge}}" alt="{{level[forloop.index].title}} Badge" />
                    </div>
                    <div class="w-3/4 pl-8">
                        <p class="h3 font-semibold mb-4">{{level[forloop.index].title}}</p>
                        <p>{{level[forloop.index].text}}</p>
                    </div>
                </article>
              </div>
          {%- endfor -%}
        </div>
    </div>
</section>
<section class="section cta_banner bg-pastel-green">
    <div class="wrapper inner w-full flex items-center justify-center">
        <a href="/specifications/{{ site.current_version}}/security-levels" class="cta-link">Read the level specifications</a>
    </div>
</section>
<section x-data="{ specificationPages: [], currentVersion: `{{site.current_version|replace: "v", ""}}` }" class="section flex flex-col justify-center items-center">
    <div class="wrapper inner w-full">
        <div class="flex justify-between items-start">
<!-- no indentation here to get markdown working with jekyll commonmark for styling the headings better -->
<div class="text w-2/3">
<div class="h3 mb-8">

## Specifications

</div>

<!-- Alpine js state for version buttons here -->
{% include specifications-versions.html %}
</div>
            <div class="w-2/4 text-green">
                {% include specifications-list.html  %}
            </div>
        </div>
    </div>
</section>