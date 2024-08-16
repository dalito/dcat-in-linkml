# DCAT in (to) LinkML

An experiment to create a linkML model that matches dcat 2.2 and dcat 3 from dcat specification in rdf.

DCAT as Owl ontology in RDF:

- DCAT, Version 2:
  - Specification, v2.2:  https://www.w3.org/ns/dcat#
  - Turtle file url: https://www.w3.org/ns/dcat2.ttl
- DCAT, Version 3: https://www.w3.org/standards/history/vocab-dcat-3/ (RDF serializations are in [DXWG GitHub repository](https://github.com/w3c/dxwg/tree/gh-pages/dcat/rdf))
  - Latest version: https://www.w3.org/TR/vocab-dcat-3/
  - Turtle file url: https://raw.githubusercontent.com/w3c/dxwg/gh-pages/dcat/rdf/dcat3.ttl (Proposed recommendation 2024-06-13, but file is last changed 2023-02-02)

Here we try a conversion with [schema-automator](https://github.com/linkml/schema-automator) from the linkML team.

First, create a virtual environment and install schema-automator. It also requires setuptools which is not listed in its dependencies (as of v0.5.2).

```cmd
py -3.12 -m venv .venv
.venv/scripts/activate
pip install schema-automator setuptools
```

The exact versions of all packages used are documented in `requirements_frozen.txt` (created by `pip freeze > requirements_frozen.txt`).

With schema-automator it is possible to import from a schema-style OWL ontology. This must be in functional syntax which can be created with [robot](https://robot.obolibrary.org/) ahead of time:

```cmd
robot convert -i dcat-source-rdf/dcat2.ttl -o dcat-source-rdf/dcat2.ofn

schemauto import-owl dcat-source-rdf/dcat2.ofn -o linkML/dcat2.yaml
```

See [linkml/README.txt](linkml/README.txt) for details of the conversion process. The obtained LinkML models (in yaml) are in [linkml/](linkml/).

**This is only a first experiment without any validation or polishing.**

It demonstrates the outcome of using standard commands/tools without tweaking options.
