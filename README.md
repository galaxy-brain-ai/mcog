
# MCog Core: A Metacognition Ontology

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub Stars](https://img.shields.io/github/stars/galaxy-brain-ai/mcog-core.svg)](https://github.com/galaxy-brain-ai/mcog-core/stargazers)
[![GitHub Issues](https://img.shields.io/github/issues/galaxy-brain-ai/mcog-core.svg)](https://github.com/galaxy-brain-ai/mcog-core/issues)

> **MCog Core v2.1 – Biomimicry & Ephemeral Cognition**  
> A domain-agnostic ontology capturing advanced metacognitive constructs, refined and expanded to mirror nature’s adaptive processes in cognitive reasoning.

![MCog Core Logo](https://raw.githubusercontent.com/galaxy-brain-ai/mcog-core/main/logo.png)

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [What's New in v2.1](#whats-new-in-v21)
- [Ontology Specification](#ontology-specification)
- [Example Usage](#example-usage)
- [Design Principles](#design-principles)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Testing](#testing)
- [Future Directions](#future-directions)
- [Contributing](#contributing)
- [License](#license)
- [Citation](#citation)
- [Contact](#contact)
- [Acknowledgements](#acknowledgements)

---

## Overview

**MCog Core** is a domain-agnostic ontology designed to represent fundamental metacognitive constructs for AI systems, cognitive architectures, decision support tools, and educational applications. Now in its **v2.1 release**, the ontology has evolved from its earlier quantum/stealth-focused design (v2.0) toward a richer, **biomimicry-inspired framework** that embraces natural, ephemeral cognitive processes—mirroring the fleeting and adaptive nature of biological thought.

---

## Key Features

- **Domain Agnostic & Modular:**  
  Designed for reuse and extension across diverse projects.
  
- **Advanced Metacognitive Modeling:**  
  Captures reasoning processes, heuristics, hypotheses, reflections, biases, and confidence assessments.
  
- **Ephemeral Cognition & Biomimicry:**  
  New classes such as `EphemeralCognitionProcess` and `BiomimeticDimension` model fleeting cognitive states and nature-inspired adaptive feedback loops.
  
- **Backward Compatibility:**  
  Retains all constructs from previous versions while adding new functionalities.
  
- **Open Source & Iteratively Developed:**  
  Continuously refined based on research insights and community feedback.

---

## What's New in v2.1

This release introduces a refined approach to representing ephemeral states and biomimetic processes:

1. **EphemeralCognitionProcess:**  
   - Models transient mental states akin to fleeting thoughts.
   - Introduces the `transientLevel` property to quantify fleetingness.
   
2. **BiomimeticDimension:**  
   - A subclass of `Reflection` capturing nature-inspired adaptive cycles.
   - Provides a metaphor for iterative reflections similar to natural processes.
   
3. **Enhanced Relationships:**  
   - New object property `hasEphemeralFocus` links fleeting cognition instances to their temporary reflections.
   
4. **Updated “Stealth Modality” Description:**  
   - Reframes stealth features to align with transient and unarticulated aspects of cognitive reasoning.
   
5. **Version Bump:**  
   - The ontology is now marked as **v2.1**—signifying a major evolutionary step in its conceptual design.

---

## Ontology Specification

The MCog Core ontology is provided in **Turtle** format. Below is an excerpt showcasing new and updated sections of the ontology:

```turtle
@prefix mcog-core: <https://github.com/galaxy-brain-ai/mcog-core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

################################################################################
# NEW BIOMIMICRY & EPHEMERAL CLASSES (V2.1)
################################################################################

mcog-core:EphemeralCognitionProcess a owl:Class ;
  rdfs:label "Ephemeral Cognition Process" ;
  rdfs:subClassOf mcog-core:ReasoningProcess ;
  dct:description """
A short-lived or transient reasoning process, analogous to fleeting thoughts in 
biological cognition. Ephemeral cognitions might never reach full articulation 
unless captured or reflected upon in time.
"""@en .

mcog-core:BiomimeticDimension a owl:Class ;
  rdfs:label "Biomimetic Dimension" ;
  rdfs:subClassOf mcog-core:Reflection ;
  dct:description """
A reflection approach or layer that emulates cycles observed in natural systems—iterative 
adaptation, emergence, and dissolution. Captures how ephemeral or stealth-like states 
arise, transform, or vanish similarly to adaptive processes in living organisms.
"""@en .

################################################################################
# NEW OBJECT PROPERTY: hasEphemeralFocus
################################################################################

mcog-core:hasEphemeralFocus a owl:ObjectProperty ;
  rdfs:label "has Ephemeral Focus" ;
  rdfs:domain mcog-core:EphemeralCognitionProcess ;
  rdfs:range mcog-core:Reflection ;
  dct:description "Indicates a reflection (or set of reflections) that momentarily captured or addressed an otherwise fleeting cognition process."@en .

################################################################################
# NEW DATATYPE PROPERTY: transientLevel
################################################################################

mcog-core:transientLevel a owl:DatatypeProperty ;
  rdfs:label "transient Level" ;
  rdfs:domain mcog-core:EphemeralCognitionProcess ;
  rdfs:range xsd:float ;
  dct:description "A measure (0.0 to 1.0) indicating how fleeting or short-lived an ephemeral cognition process is. Higher values suggest more rapid dissipation."@en .
```

> A [complete Turtle file](https://github.com/galaxy-brain-ai/mcog-core/blob/main/mcog-core.ttl) is provided for full reference.

---

## Example Usage

Below is an example demonstrating how to create an instance of an ephemeral cognition process and link it to a biomimetic reflection:

```turtle
@prefix mcog-core: <https://github.com/galaxy-brain-ai/mcog-core#> .
@prefix ex: <http://example.org/resource/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

# Define an ephemeral cognition instance with a high transient level
ex:fleeting-idea-001 a mcog-core:EphemeralCognitionProcess ;
  mcog-core:transientLevel "0.85"^^xsd:float ;
  mcog-core:usesHeuristic ex:heuristic-fuzzy-imagery .

ex:heuristic-fuzzy-imagery a mcog-core:Heuristic ;
  mcog-core:heuristicName "Fuzzy, imagery-based mental shortcut"@en .

# Define a biomimetic reflection capturing the fleeting idea
ex:brief-reflection-001 a mcog-core:BiomimeticDimension ;
  mcog-core:reflectionTimestamp "2025-01-19T10:00:00Z"^^xsd:dateTime ;
  mcog-core:reflectionText "A short-lived intuitive flash about an approach to solve problem X, reminiscent of ephemeral patterns in nature."@en ;
  mcog-core:reflectsOn ex:fleeting-idea-001 .

# Link the ephemeral cognition to the reflection
ex:fleeting-idea-001 mcog-core:hasEphemeralFocus ex:brief-reflection-001 .
```

---

## Design Principles

- **Clarity & Flexibility:**  
    Every class and property is clearly defined using descriptive annotations, ensuring broad applicability without over-restrictive constraints.
    
- **Iterative & Adaptive Development:**  
    `MCog Core` is continually enhanced by incorporating real-world insights from research (including our latest biomimicry-inspired extensions).
    
- **Backward Compatibility:**  
    Updates and new features (v2.1) maintain all existing classes and relationships from earlier versions.
    

---

## Installation

1. **Clone the Repository:**
    
    ```bash
    git clone https://github.com/galaxy-brain-ai/mcog-core.git
    cd mcog-core
    ```
    
2. **Download the Ontology File:**
    
    The main ontology file is available in Turtle format as [`mcog-core.ttl`](https://github.com/galaxy-brain-ai/mcog-core/blob/main/mcog-core.ttl).
    
3. **Integrate into Your Project:**
    
    Import the ontology file into your semantic framework or RDF-aware system as required.
    

---

## Usage

To integrate `MCog Core` into your application:

- **For RDF-based reasoning:**  
    Load `mcog-core.ttl` into your RDF store or triple store.
    
- **For programmatic access:**  
    Use your favorite ontology parser (e.g., [Apache Jena](https://jena.apache.org/) for Java, [RDFlib](https://rdflib.readthedocs.io/) for Python) to access and traverse the metacognitive constructs.
    
- **For research and demonstration purposes:**  
    Utilize provided examples to model reasoning processes, capture ephemeral cognitions, and record adaptive reflections.
    

---

## Configuration

- **Customization:**  
    Modify or extend classes and properties as necessary to suit your domain-specific needs.
    
- **Namespaces:**  
    Ensure your tools recognize the namespace `https://github.com/galaxy-brain-ai/mcog-core#` for proper linking of ontology components.
    

---

## Testing

For automated testing of your ontology:

1. **Validate the Turtle File:**  
    Use ontology validation tools like the [W3C RDF Validator](https://www.w3.org/RDF/Validator/) or [OntoGraf](https://protege.stanford.edu/plugins/owl/ontograph.html).
    
2. **Run SPARQL Queries:**  
    Test specific reasoning cases using SPARQL queries to ensure expected inferences and mappings.
    

---

## Future Directions

Planned enhancements include:

- **Bias Taxonomy Expansion:**  
    Develop a detailed hierarchical representation of cognitive biases.
    
- **Enhanced Heuristic Modeling:**  
    Provide more granular definitions and examples for diverse heuristic approaches.
    
- **Integration with Cognitive Architectures:**  
    Explore integration pathways with existing cognitive and neural network models.
    
- **Additional Reflective Layers:**  
    Further refine the relationship between fleeting, subconscious states and fully articulated reflections.
    

---

## Contributing

All additions welcome! If you have ideas, improvements, or find issues:

- **Issues & Pull Requests:**  
    Please open issues or submit pull requests via the SOURCE [GitHub repository](https://github.com/galaxy-brain-ai/mcog-core).
    
- **Guidelines:**  
    We welcome contributions to MCog Core! If you have suggestions for improvements or extensions, please open an issue or submit a pull request on this repository.
    

---

## License

`MCog Core` is distributed under the [Creative Commons Attribution 4.0 International (CC BY 4.0) license](https://creativecommons.org/licenses/by/4.0/).

---

## Citation

If you use `MCog Core` in your research or applications, please cite the project as follows:

> **Shep Bryan, Galaxy Brain AI. (2025). MCog Core: A Metacognition Ontology (Version 2.1 – Biomimicry & Ephemeral Cognition) [Ontology Resource].** Retrieved from [https://github.com/galaxy-brain-ai/mcog-core](https://github.com/galaxy-brain-ai/mcog-core).

---

## Contact

For questions, feedback, or further collaboration:

**David Youngblood**  
**[@TheDavidYoungblood](https://github.com/thedavidyoungblood)**  
[LinkedIn](https://www.linkedin.com/in/thedavidyoungblood/) • [Medium](https://medium.com/@thedavidyoungblood) • [Twitter/X](https://x.com/TheDavidYB)

---

## Acknowledgements

- Special thanks to the original `MCog Core` authors and community contributors.
- Research enhancements provided by David Youngblood at LouminAI Labs, whose interdisciplinary insights continue to drive the evolution of this ontology.
- Gratitude to all those in the open-source and academic communities for their invaluable feedback.

---

_Empowering cognitive modeling one fleeting thought at a time—join us on the journey toward a more reflective and adaptive digital age!_
