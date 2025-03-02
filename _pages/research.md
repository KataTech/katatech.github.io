---
layout: page
title: research
permalink: /research/
description: an overview of past research projects
nav: true
nav_order: 3
horizontal: false
---

**For publication list, please refer to my [Google Scholar](https://scholar.google.com/citations?user=fqzc5pEAAAAJ&hl=en).**

<br/>

#### **MIT** 

*Still in the problem formulation and exploration phase.. but some questions of interest include:*
* **Performative Prediction.** Modern machine learning deployments carry feedback structure. In particular, their predictions or generations can affect the very relations they seek to model. In statistical terms, we need to better understand learning over non-IID settings. Some key interests of mine focus on specific *structure* of said non-IID data motivated by real-world social and strategic interactions. For more, see this [survey](https://arxiv.org/abs/2310.16608). 
* **Antitrust & Safety.** How can we provide tools and insights for regulators to combat harmful deployment of data-driven algorithms? What type of "sensors" are useful indications of failures? What failure modes should we be concerned about? And what mathematically-driven evidence is legally useful? 
* **Collective Decision-Making with Heterogeneity.** How can decision-making systems cater to diverse objectives and preferences? Can we identify and estimate mixtures of rational preferences from observational data? How should decisions be made amidst diverse preferences? 

I am excited about abstration and theory motivated by these important problems, with the hope of generating insights that help us better understand the benefits and harms of using data-driven decision systems (or "AI"). If these questions peak your interests too, please feel free to reach me. 

<hr/>

#### **Rice University**

Advised by [Dr. C&eacute;sar A. Uribe](https://cauribe.rice.edu/) and [Dr. Lydia Beaudrot](https://lydiabeaudrot.weebly.com/).

**TL;DR:** Food webs are models for species interaction, which capture significant information about an ecosystem. A formal notion of distance between food webs can then enable scaled predictions of ecological disturbances. We formalize distances between food webs using tools from Optimal Transport. In particular, we (1) show that Gromov-Wasserstein distance metricizes food webs based on shared species functional roles and (2) developed a novel graph regression model (i.e. Euclidean inputs and Graph outputs) using the Bures-Wasserstein distance. 

[1] Zalles, A., **Hung, K.**, et al. [An Optimal Transport Approach for Network Regression](https://arxiv.org/abs/2406.12204). IEEE CCTA 2024. 

[2] **Hung, K.**, Zalles, A., et al. [Towards Ecological Network Analysis with Gromov-Wasserstein Distances](https://www.climatechange.ai/papers/iclr2024/6). ICLR 2024 Workshop on Tackling Climate Change with Machine Learning.

[3] Zalles, A., **Hung, K.**, et al. [Network Regression with Wasserstein Distances](/assets/papers/zalles2023_network_regression.pdf). NeurIPS 2023 Workshop on Optimal Transport and Machine Learning.

<div class="row mt-2">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/research/food-web-ot.png" title="A Gromov-Wasserstein Approach for Food Web Network Analysis" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/research/network-reg-ot.png" title="Network Regression with Wasserstein Distances" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<hr/>

#### **New York University**
Advised by [Dr. Esteban G. Tabak](https://cims.nyu.edu/~tabak/). Supported by the [AM-SURE](https://math.nyu.edu/dynamic/research/pages/research-and-training-group-mathematical-modeling-and-simulation/activities/amsure/) program, funded by NSF.

**TL;DR:** Often times, your data is affected by variables that should be excluded from your analysis (for ex. batch effect and protected attributes such as race, gender, socioeconomic class). We developed a theoretical framework for reducing the unwanted variability in our data distribution via optimal transport. Future extensions include personalization, latent factor discovery, and semi-supervised variability reduction! 

<div class="row mt-2" style="height: 35rem;">
    <div class="col-sm-6 mt-3 mt-md-0">
        <iframe src="/assets/pdf/var-reduce-ot-presentation.pdf" width="100%" height="50%"></iframe>
        <br>
        <p>
            <a href="/assets/pdf/var-reduce-ot-presentation.pdf" target="_blank" rel="noopener noreferrer">
                <!-- You can use an icon or text as a link for the PDF viewer -->
                View Slides (PDF)
            </a>
        </p>
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        <iframe src="/assets/pdf/var-reduce-ot-paper.pdf" width="100%" height="95%"></iframe>
        <br>
        <p>
            <a href="/assets/pdf/var-reduce-ot-paper.pdf" target="_blank" rel="noopener noreferrer">
                <!-- You can use an icon or text as a link for the PDF viewer -->
                View Paper (PDF)
            </a>
        </p>
    </div>
</div>

<hr/>

#### **Berkeley AI Research**

Advised by [Dr. Alison Gopnik](http://www.gopniklab.berkeley.edu/alison) and [Eunice Yiu](https://www.linkedin.com/in/euniceyiu). Supported by the [SUPERB](https://eecs.berkeley.edu/resources/undergrads/research/superb) and [BAIR](https://bair.berkeley.edu/reu.html) NSF REU programs. 

**TL;DR:** Have you ever contrasted the intelligence of children with adults, and maybe even artificial intelligence? Children are known to learn quickly and generalize accurately with little data to their disposal, contrary to deep neural networks and other modern machine learning frameworks. Our analysis is two-fold: (1) to understand the discrepancies in children and adults' exploration v.s. exploitation modalities through fitting experimental data against reinforcement learning models, and (2) to understand the degree in which popular Q-learning-based RL algorithms can truly mimic what we observe within humans.
<div class="row mt-2">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/research/berkeley.png" title="BAIR" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        <iframe src="/assets/pdf/bair-rl-presentation.pdf" width="100%" height="85%"></iframe>
        <br>
        <p>
            <a href="/assets/pdf/bair-rl-presentation.pdf" target="_blank" rel="noopener noreferrer">
                <!-- You can use an icon or text as a link for the PDF viewer -->
                View Slides (PDF)
            </a>
        </p>
    </div>
</div>
