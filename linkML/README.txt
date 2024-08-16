# Log for conversion

## DCAT 2

Note, even more detailed logs than below are created if `-vvv` option is used.

```cmd
(.venv) λ schemauto -v import-owl dcat-source-rdf/dcat2.ofn -o linkML/dcat2.yaml
INFO:root:Log level=1
.........k.........k
ERROR:root:Overwriting class_uri for {'class_uri': 'rdfs:Resource'} to dcat:Resource
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/contributor'} to dct:contributor
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/coverage'} to dct:coverage
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/creator'} to dct:creator
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/description'} to dct:description
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/language'} to dct:language
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/publisher'} to dct:publisher
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/rights'} to dct:rights
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/source'} to dct:source
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/type'} to dct:type
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/dcam/rangeIncludes'} to sdo:rangeIncludes
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:cannot handle anon object child properties for SubObjectPropertyOf(subObjectPropertyExpression=SubObjectPropertyExpression(v=ObjectPropertyChain(objectPropertyExpressions=[ObjectProperty(v='dcat:accessService'), ObjectProperty(v='dcat:endpointURL')], annotations=[])), superObjectPropertyExpression=ObjectPropertyExpression(v=ObjectProperty(v='dcat:accessURL')), annotations=[])
ERROR:root:Box is not known
ERROR:root:ISO3166 is not known
ERROR:root:ISO639-2 is not known
ERROR:root:ISO639-3 is not known
ERROR:root:Period is not known
ERROR:root:Point is not known
ERROR:root:RFC1766 is not known
ERROR:root:RFC3066 is not known
ERROR:root:RFC3066 is not known
ERROR:root:RFC4646 is not known
ERROR:root:RFC4646 is not known
ERROR:root:RFC5646 is not known
ERROR:root:RFC5646 is not known
ERROR:root:URI is not known
ERROR:root:W3CDTF is not known
ERROR:root: is not known
ERROR:root:DCMIType is not known
ERROR:root:DDC is not known
ERROR:root:IMT is not known
ERROR:root:LCC is not known
ERROR:root:LCSH is not known
ERROR:root:MESH is not known
ERROR:root:NLM is not known
ERROR:root:TGN is not known
ERROR:root:UDC is not known
ERROR:root:instructionalMethod is not known
ERROR:root:instructionalMethod is not known
ERROR:root:instructionalMethod is not known
ERROR:root:provenance is not known
ERROR:root:provenance is not known
ERROR:root:provenance is not known
ERROR:root:rightsHolder is not known
ERROR:root:rightsHolder is not known
ERROR:root:rightsHolder is not known
```

The produced LinkML model passes the check with the LinkML validator:

```cmd
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ linkml validate -s linkML\dcat2.yaml
No issues found
```

But creating mermeid ER-diagram or a plantuml visualization fails:

```cmd
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ linkml generate erdiagram linkml/dcat2.yaml
WARNING:rdflib.term:C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml\.venv\Lib\site-packages\linkml_runtime\linkml_model\model\schema\types does not look like a valid URI, trying to serialize this will break.
ValueError: No such class as "Concept"

C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ linkml generate plantuml linkml/dcat2.yaml
ValueError: File "dcat2.yaml", line 461, col 12 slot: theme - unrecognized range (Concept)
```

## DCAT3

```
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ schemauto -v import-owl dcat-source-rdf/dcat3.ofn -o linkML/dcat3.yaml
INFO:root:Log level=1
.........k.........k...
ERROR:root:Overwriting class_uri for {'class_uri': 'rdfs:Resource'} to dcat:Resource
ERROR:root:Overwriting slot_uri for {'slot_uri': 'xhv:first'} to dcat:first
ERROR:root:Overwriting slot_uri for {'slot_uri': 'pav:hasVersion'} to dcat:hasVersion
ERROR:root:Overwriting slot_uri for {'slot_uri': 'xhv:last'} to dcat:last
ERROR:root:Overwriting slot_uri for {'slot_uri': 'xhv:prev'} to dcat:prev
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/contributor'} to dcterms:contributor
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/coverage'} to dcterms:coverage
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/creator'} to dcterms:creator
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/description'} to dcterms:description
ERROR:root:Overwriting slot_uri for {'slot_uri': 'dcat:isVersionOf'} to dcterms:isVersionOf
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/language'} to dcterms:language
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/publisher'} to dcterms:publisher
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/rights'} to dcterms:rights
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/source'} to dcterms:source
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/elements/1.1/type'} to dcterms:type
ERROR:root:Overwriting slot_uri for {'slot_uri': 'http://purl.org/dc/dcam/rangeIncludes'} to sdo:rangeIncludes
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:TODO
ERROR:root:cannot handle anon object child properties for SubObjectPropertyOf(subObjectPropertyExpression=SubObjectPropertyExpression(v=ObjectPropertyChain(objectPropertyExpressions=[ObjectProperty(v='dcat:accessService'), ObjectProperty(v='dcat:endpointURL')], annotations=[])), superObjectPropertyExpression=ObjectPropertyExpression(v=ObjectProperty(v='dcat:accessURL')), annotations=[])
ERROR:root:Box is not known
ERROR:root:ISO3166 is not known
ERROR:root:ISO639-2 is not known
ERROR:root:ISO639-3 is not known
ERROR:root:Period is not known
ERROR:root:Point is not known
ERROR:root:RFC1766 is not known
ERROR:root:RFC3066 is not known
ERROR:root:RFC3066 is not known
ERROR:root:RFC4646 is not known
ERROR:root:RFC4646 is not known
ERROR:root:RFC5646 is not known
ERROR:root:RFC5646 is not known
ERROR:root:URI is not known
ERROR:root:W3CDTF is not known
ERROR:root: is not known
ERROR:root:DCMIType is not known
ERROR:root:DDC is not known
ERROR:root:IMT is not known
ERROR:root:LCC is not known
ERROR:root:LCSH is not known
ERROR:root:MESH is not known
ERROR:root:NLM is not known
ERROR:root:TGN is not known
ERROR:root:UDC is not known
ERROR:root:instructionalMethod is not known
ERROR:root:instructionalMethod is not known
ERROR:root:instructionalMethod is not known
ERROR:root:provenance is not known
ERROR:root:provenance is not known
ERROR:root:provenance is not known
ERROR:root:rightsHolder is not known
ERROR:root:rightsHolder is not known
ERROR:root:rightsHolder is not known
```

The produced LinkML model passes the check with the LinkML validator:

```cmd
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ linkml validate -s linkML\dcat3.yaml
No issues found
```

But creating mermeid ER-diagram or a plantuml visualization fails:

```cmd
C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ linkml generate erdiagram linkml/dcat3.yaml
WARNING:rdflib.term:C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml\.venv\Lib\site-packages\linkml_runtime\linkml_model\model\schema\types does not look like a valid URI, trying to serialize this will break.
ValueError: No such class as "Concept"

C:\Users\dlinke\MyProg_local\gh-dalito\dcat-in-linkml (main -> origin)
(.venv) λ linkml generate plantuml linkml/dcat3.yaml
RecursionError: maximum recursion depth exceeded
(...)
ValueError: File "dcat3.yaml", line 18, col 11 Slot: "hasVersion" - recursive is_a reference: hasVersion
```
