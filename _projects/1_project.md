---
layout: page
title: Engineering Demonstration
description: with background image
img: assets/img/mambavision_pipeline_diagram.png
importance: 1
category: work
related_publications: false
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/mambavision_pipeline_diagram.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Portage de Mambavision
</div>

<a href="https://github.com/phealice/demo_inge" class="btn btn-sm z-depth-0" role="button">
  <i class="fa-brands fa-github"></i> Repo
</a>

Pipeline de déploiement production pour MambaVision, un modèle de vision basé sur l'architecture Mamba (State Space Models). Le projet couvre l'export des poids PyTorch vers ONNX via un patch de l'implémentation de référence SSM, l'inférence via ONNXRuntime avec fallback CPU/CUDA/TensorRT, et l'intégration dans un nœud ROS2 Jazzy packagé dans une image Docker multi-cible (x86 GPU cloud, Jetson ARM64). Un pipeline CI/CD GitHub Actions automatise l'export du modèle sur tag git et la construction des images versionnées poussées sur GHCR. La compilation du moteur TensorRT est déléguée au premier lancement sur le hardware cible pour garantir la portabilité des artefacts.