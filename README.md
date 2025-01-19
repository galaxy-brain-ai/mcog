# MCog Core: A Metacognition Ontology

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

## Overview

MCog Core is a domain-agnostic ontology designed to represent fundamental metacognitive constructs. It provides a reusable and extensible framework for modeling reasoning, reflection, and learning processes. This ontology is particularly relevant for AI systems, cognitive architectures, decision support tools, and educational applications that require a metacognitive layer.

## Key Features

*   **Domain Agnostic:**  MCog Core is intentionally designed to be independent of any specific domain.
*   **Focus on Metacognition:** The ontology captures core metacognitive elements, including:
    *   `ReasoningProcess`: Different types of reasoning (currently represented at a high level).
    *   `Heuristic`: Mental shortcuts or rules of thumb.
    *   `Hypothesis`: Testable assumptions or propositions.
    *   `Reflection`: Introspective analysis of reasoning processes.
    *   `Bias`: Systematic errors in judgment.
    *   `ConfidenceAssessment`: Evaluation of certainty.
    *   `FeedbackLoop`: Mechanisms for refining reasoning.
    *   `LearningProcess`: Processes for updating knowledge and strategies (with basic representation of double and triple-loop learning).
*   **Modularity:** Designed to be imported and extended by other ontologies.
*   **Extensibility:**  The ontology is designed to be extended with more specific metacognitive concepts as needed.
*   **Open Source:** Released under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

## Ontology File

The MCog Core ontology is available in Turtle (.ttl) format: [mcog-core.ttl](mcog-core.ttl)

## Design Principles

*   **Clarity:** Terms are defined clearly and concisely using `dct:description` annotations.
*   **Flexibility:** The ontology avoids overly restrictive constraints to allow for flexibility in real-world applications.
*   **Reusability:** The domain-agnostic nature of MCog Core makes it suitable for reuse in a variety of applications.
*   **Iterative Development:** MCog Core is intended to be refined and expanded iteratively based on feedback and practical use.

## Example Usage

```turtle
# Example instance of a Hypothesis with a ConfidenceAssessment

@prefix mcog-core: <https://github.com/galaxy-brain-ai/mcog-core#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<MyHypothesis> a mcog-core:Hypothesis ;
  mcog-core:hypothesisContent "This is an example hypothesis."@en ;
  mcog-core:hasConfidenceAssessment [
    a mcog-core:ConfidenceAssessment ;
    mcog-core:confidenceValue "0.8"^^xsd:float ;
    mcog-core:confidenceRationale "Based on initial evidence."@en
  ] .
```

## Future Directions

Future development of MCog Core may involve:

*   **Bias Taxonomy:**  Expanding the `Bias` class to include a hierarchy of specific types of biases.
*   **Heuristic Modeling:**  Developing a more detailed representation of heuristics.
*   **Formalization of Uncertainty:**  Adding more nuanced representations of uncertainty and confidence.
*   **Integration with Cognitive Architectures:** Exploring integration with existing cognitive architectures.

## Contributing

We welcome contributions to MCog Core! If you have suggestions for improvements or extensions, please open an issue or submit a pull request on this repository.

## License

MCog Core is released under the [Creative Commons Attribution 4.0 International (CC BY 4.0) license](https://creativecommons.org/licenses/by/4.0/).

## Citation

If you use MCog Core in your research or applications, please cite it as follows:

Shep Bryan. (2025). MCog Core: A Metacognition Ontology (Version 1.0) [Ontology]. Retrieved from [[Github](https://github.com/galaxy-brain-ai/mcog)]

## Contact

Shep Bryan, Galaxy Brain
shep@galaxy-brain.ai
galaxy-brain.aii
