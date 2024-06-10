---
date: "2022-06-05"
description: Some of the personal projects I recently worked on
title: Projects
---


## <a href="https://github.com/glothriel/wormhole">Wormhole <i class="fa fa-github"></i></a>

Allows exposing a kubernetes `kind: Service` between different clusters via L4 reverse tunnels over wireguard, just by using annotations. Similar to ngrok, teleport or skupper, but implemented specifically for Kubernetes. Used at production at Piwik PRO.

## <a href="https://github.com/glothriel/grf">GRF <i class="fa fa-github"></i></a>

Gin REST Framework - DRF-style CRUD REST framework for go, using 1.18 generics instead of code generation. Interesting POC, but due to lack of a real use-case not polished enough for any serious usage.

## <a href="https://github.com/glothriel/npviz">NpViz <i class="fa fa-github"></i></a>

NpViz is a simple utility, that allows viewing all allowed connections between kubernetes pods using either active kubectl context or static directory with YAML resources as a source. It has a simple web-based UI, that can be interactively interpreted by the user. It was a single weekend project.

