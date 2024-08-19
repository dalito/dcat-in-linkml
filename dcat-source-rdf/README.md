# Logs robot

Conversion to ofn with robot runs successfully without errors for DCAT2.

```cmd
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ C:\portable-apps\robot\robot --version
ROBOT version 1.9.6
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ C:\portable-apps\robot\robot convert -i dcat-source-rdf/dcat2.ttl -o dcat-source-rdf/dcat2.ofn
```

For DCAT3 version https://github.com/w3c/dxwg/commit/f03a6dc8c1f00be1ac94bde465440833377400d3 robot reports three unparsable triples:

```
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ C:\portable-apps\robot\robot convert -i dcat-source-rdf/dcat3.ttl -o dcat-source-rdf/dcat3.ofn
2024-08-16 09:14:12,903 ERROR org.obolibrary.robot.IOHelper - Input ontology contains 3 triple(s) that could not be parsed:
 - <http://www.w3.org/ns/dcat#previousVersion> <http://www.w3.org/2002/07/owl#equivalentProperty> <http://purl.org/pav/previousVersion>.
 - <http://www.w3.org/ns/dcat#version> <http://www.w3.org/2002/07/owl#equivalentProperty> <http://purl.org/pav/version>.
 - <http://www.w3.org/ns/dcat#hasCurrentVersion> <http://www.w3.org/2002/07/owl#equivalentProperty> <http://purl.org/pav/hasCurrentVersion>.
```

- dcat3-ap_shapes_en-names.ttl from (uses natural names) from https://github.com/SEMICeu/DCAT-AP/blob/master/releases/3.0.0/html/shacl/shapes.ttl
- dcat3-ap_3_SHACL.ttl (uses UUIDs) from https://github.com/SEMICeu/DCAT-AP/blob/master/releases/3.0.0/shacl/dcat-ap-SHACL.ttl

