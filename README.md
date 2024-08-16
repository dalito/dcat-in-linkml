# DCAT in (to) LinkML

An experiment to create a linkML model that matches dcat 2.2 and dcat 3 from dcat specification in rdf.

DCAT as Owl ontology in RDF:

- DCAT, Version 2:
  - Specification, v2.2:  https://www.w3.org/ns/dcat#
  - Turtle file url: https://www.w3.org/ns/dcat2.ttl
- DCAT, Version 3: https://www.w3.org/standards/history/vocab-dcat-3/ (RDF serializations are in [DXWG GitHub repository](https://github.com/w3c/dxwg/tree/gh-pages/dcat/rdf))
  - Latest version: https://www.w3.org/TR/vocab-dcat-3/
  - Turtle file url: https://github.com/w3c/dxwg/tree/gh-pages/dcat/rdf/dcat3.ttl (Proposed recommendation, 2024-06-13)

We use linkML schema-automator for the initial conversion.

First, create a virtual environment

```cmd

py -3.12 -m venv .venv
.venv/scripts/activate

pip install schema-automator

```

It is also possible (not yet tried) to import from a schema-style OWL ontology. This must be in functional syntax which can be created with [robot](https://robot.obolibrary.org/) ahead of time:

```cmd
robot convert -i dcat-source-rdf/dcat2.ttl -o dcat-source-rdf/dcat2.ofn

# or locally
C:\dev\openjdk\jdk-19\bin\java  -jar C:\portable-apps\robot\robot.jar convert -i dcat-source-rdf/dcat2.ttl -o dcat-source-rdf/dcat2.ofn

schemauto import-owl dcat-source-rdf/dcat2.ofn -o linkML/dcat2.yaml
```
