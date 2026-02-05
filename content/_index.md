---
title: Dragonfly
layout: hextra-home
---

<div style="display: flex; flex-direction: row; gap: 3rem; align-items: center; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 400px;">

{{< hextra/hero-headline >}}
metal, managed.
{{< /hextra/hero-headline >}}

{{< hextra/hero-subtitle >}}
Automatic discovery and installation for all your servers, made easy. Works on the cloud, on-premises, and at the edge.
{{< /hextra/hero-subtitle >}}

<div class="hx:mt-6 hx:mb-6 hx:flex hx:gap-3">
{{< hextra/hero-button text="Get Started" link="dragonfly" >}}
{{< hextra/hero-button text="Learn About Jetpack" link="jetpack" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);" >}}
</div>

  </div>
  <div style="flex: 1; min-width: 300px; max-width: 450px; margin: 2rem;">
    <img src="/images/machines-light.png" alt="Dragonfly Machines Dashboard" style="width: 100%; border-radius: 0.5rem; box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);" class="hx:dark:hidden" />
    <img src="/images/machines.png" alt="Dragonfly Machines Dashboard" style="width: 100%; border-radius: 0.5rem; box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);" class="hx:hidden hx:dark:block" />
  </div>
</div>

{{< hextra/feature-grid >}}
  {{< hextra/feature-card
    title="Dragonfly"
    subtitle="Bare metal provisioning and PXE boot management. Deploy operating systems across your infrastructure with ease."
    link="dragonfly"
    icon="server"
  >}}
  {{< hextra/feature-card
    title="Jetpack"
    subtitle="Next-generation configuration management. A modern approach to infrastructure automation that learns from Ansible's lessons."
    link="jetpack"
    icon="chip"
  >}}
  {{< hextra/feature-card
    title="Open Source"
    subtitle="Built in the open. All Dragonfly tools are free and open source, designed for transparency and community contribution."
    icon="code"
  >}}
{{< /hextra/feature-grid >}}
