================================================================
INSTRUCTIONS
================================================================
1. For each file below, create a new file on GitHub at the path shown
2. Copy everything between the START and END markers into that file
3. projects.md goes in _pages/
4. All other files go in _projects/
5. Upload cover images to assets/img/projects/ matching the img: filename
================================================================


================================================================
FILE: _pages/projects.md
================================================================
---
layout: page
title: Projects
permalink: /projects/
description: A collection of robotics, research, and engineering projects spanning competition science, university coursework, and independent work.
nav: true
nav_order: 3
display_categories: [robotics, research, engineering]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}
{% else %}
{% assign sorted_projects = site.projects | sort: "importance" %}
{% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>


================================================================
FILE: _projects/camera_mount.md
================================================================
---
layout: page
title: 2-DOF Pan-Tilt Camera System
description: Servo-actuated pan-tilt camera mount for URC Mars Rover. Custom 1:2 spur gear train, 608 ball bearing, SolidWorks, PLA FDM. 360° pan, 180° tilt.
img: assets/img/projects/camera_mount.jpg
importance: 1
category: robotics
related_publications: false
---

## Overview
Add project description here.

## Design
Add SolidWorks renders, exploded views, and key design decisions here.

## Links
- [Full Report (PDF)](#)


================================================================
FILE: _projects/dual_gps.md
================================================================
---
layout: page
title: Dual GPS Antenna Mounts
description: Primary and secondary GPS antenna mounts with 1-metre baseline separation for spatial diversity and improved signal reliability. URC Mars Rover, SolidWorks, PLA FDM.
img: assets/img/projects/dual_gps.jpg
importance: 2
category: robotics
related_publications: false
---

## Overview
Add project description here.

## Design
Add SolidWorks renders and key design decisions here.


================================================================
FILE: _projects/grasp_detection.md
================================================================
---
layout: page
title: Power Grasp Detection on 3D Objects via Multi-Height Mesh Analysis
description: Grasp planning algorithm for 3D objects using multi-height mesh analysis. Referred by Dr. Gary Bone, PhD. MATLAB, computational geometry, algorithm design.
img: assets/img/projects/grasp_detection.jpg
importance: 3
category: robotics
related_publications: false
---

## Overview
Add project description here.

## Methods
Add methodology, algorithm diagrams, and results here.


================================================================
FILE: _projects/end_effector.md
================================================================
---
layout: page
title: Robotic End Effector System
description: Robotic end effector design and integration for Q-arm platform. McMaster University Project 1. Manufacturing, robotics, Q-arm.
img: assets/img/projects/end_effector.jpg
importance: 4
category: robotics
related_publications: false
---

## Overview
Add project description here.

## Design & Integration
Add design details, renders, and results here.


================================================================
FILE: _projects/point_cloud.md
================================================================
---
layout: page
title: 3D Point Cloud Processing with ROS2 and PCL
description: Experimental project testing ROS2 and PCL library for 3D point cloud processing. Robotics perception, C++, Linux.
img: assets/img/projects/point_cloud.jpg
importance: 5
category: robotics
related_publications: false
---

## Overview
Add project description here.

## Implementation
Add code snippets, results, and visualizations here.


================================================================
FILE: _projects/new_robot.md
================================================================
---
layout: page
title: New Robot Project
description: Incoming robotics project — robotics engineering, embedded systems, simulation. April 2026 – August 2026.
img: assets/img/projects/new_robot.jpg
importance: 6
category: robotics
related_publications: false
---

## Overview
Project in progress. Details to be added.


================================================================
FILE: _projects/isef_lupus.md
================================================================
---
layout: page
title: Genetic Analysis of CD16+/- Monocytes and CD4+ T Cells for SLE Diagnostic Tool
description: Computational immunogenomics research identifying novel gene signatures in CD16+/- monocytes and CD4+ T lymphocytes for Systemic Lupus Erythematosus diagnosis. Presented at BASEF 2024, CWSF 2024, ISEF 2024 — 4th Place Grand Award.
img: assets/img/projects/isef_lupus.jpg
importance: 1
category: research
related_publications: true
---

## Overview
Add project description here.

## Methods
Add methodology, data analysis, and results here.

## Awards
- ISEF 2024 — Fourth Place Grand Award, Biomedical and Health Sciences
- CWSF 2024 — Silver Merit Award
- BASEF 2024 — Best in Fair, Pinnacle Award


================================================================
FILE: _projects/nitrous_oxide.md
================================================================
---
layout: page
title: Nitrous Oxide Reduction in an Industrial Wet Scrubber Utilizing NosZ Reductase and P. denitrificans
description: Chemical engineering research on biological nitrous oxide reduction in industrial wet scrubbers. 3D simulation, gas treatment systems. Presented at BASEF 2023, CWSF 2023, Ingenious+ 2025.
img: assets/img/projects/nitrous_oxide.jpg
importance: 2
category: research
related_publications: false
---

## Overview
Add project description here.

## Methods
Add methodology, simulation details, and results here.


================================================================
FILE: _projects/project_aura.md
================================================================
---
layout: page
title: Project AURA
description: Independent research project at the intersection of computer engineering, neuroscience, and biomedical engineering. May 2025 – June 2025.
img: assets/img/projects/project_aura.jpg
importance: 3
category: research
related_publications: false
---

## Overview
Add project description here.

## Methods
Add methodology and results here.


================================================================
FILE: _projects/carbon_capture.md
================================================================
---
layout: page
title: Carbon Capture Depletion Using Catalyzed Photosynthesis to Promote Crop Growth
description: Environmental engineering research on catalyzed photosynthesis for carbon capture and crop growth promotion. Published in Canadian Science Fair Journal (CSFJ). Presented at BASEF 2022, CWSF 2022.
img: assets/img/projects/carbon_capture.jpg
importance: 4
category: research
related_publications: true
---

## Overview
Add project description here.

## Methods
Add methodology and results here.


================================================================
FILE: _projects/covid_mask.md
================================================================
---
layout: page
title: Experimental Evaluation of Household Fabrics for Aerosol Filtration and Improved COVID-19 Mask Design
description: Material science research evaluating household fabric filtration performance for COVID-19 mask development. Mask filtration, particle filtration efficiency, public health. Presented at BASEF 2021.
img: assets/img/projects/covid_mask.jpg
importance: 5
category: research
related_publications: false
---

## Overview
Add project description here.

## Methods
Add methodology, filtration testing data, and results here.


================================================================
FILE: _projects/canafarm.md
================================================================
---
layout: page
title: CanaFarm Robotics
description: Robotics and environmental engineering project for automated farming systems. Systems engineering, environmental engineering. Presented at BASEF 2020.
img: assets/img/projects/canafarm.jpg
importance: 6
category: research
related_publications: false
---

## Overview
Add project description here.

## Design
Add design details and results here.


================================================================
FILE: _projects/gripeasy.md
================================================================
---
layout: page
title: Grizzly Paws — GripEase
description: Rehabilitation-focused assistive device design. Materials engineering, rehabilitation engineering. McMaster University Project 3. January 2026 – April 2026.
img: assets/img/projects/gripeasy.jpg
importance: 1
category: engineering
related_publications: false
---

## Overview
Add project description here.

## Design
Add design details, renders, and testing results here.


================================================================
FILE: _projects/algae_wastewater.md
================================================================
---
layout: page
title: Algae Wastewater Filtration System
description: Biochemical and materials engineering design of an algae-based wastewater filtration system. McMaster University Project 2. January 2026 – April 2026.
img: assets/img/projects/algae_wastewater.jpg
importance: 2
category: engineering
related_publications: false
---

## Overview
Add project description here.

## Design
Add design details and results here.


================================================================
FILE: _projects/balsa_bridge.md
================================================================
---
layout: page
title: Balsa Bridge Project
description: Structural engineering design and competition build. Material science, civil and structural engineering. 3rd Place Force, 5th Overall — PEO Bridge Building Competition 2024.
img: assets/img/projects/balsa_bridge.jpg
importance: 3
category: engineering
related_publications: false
---

## Overview
Add project description here.

## Design & Results
Add design details, load testing results, and competition outcome here.

