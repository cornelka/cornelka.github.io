https://cornelka.github.io/sol_kc/data.ttl
https://cornelka.github.io/sol_kc.ttl


* What happens when you try the FOAF query?
The query only has a reference to the FOAF vocabulary and tries to display results based only on that vocabulary.
Data described directly with the FOAF vocabulary will shown.
Also data described in any other vocabulary will be shown, if the correct concepts from FOAF are connected to the other vocabulary.
In this case we need to minimaly connect 2 foaf classes (Image + Person) and 2 properties (depicts + name).

A connection between 2(or more) vocabularies can be made with another vocabulary that describes a set of relations and constraints between different concepts. RDFS and OWL are both such vocabularies. These describe in essense some kind of logic.

* How does this show semantics in action?
We describe the connections/links between FOAF and our own vocabulary with eg. RDFS + OWL AND we provide logic rules to the reasoner that implement these RDFS or OWL connections/links. Combining these 2 the reasoner can derive new facts automatically. With these new facts, the data originally described in our own vocabulary can now also be described with FOAF vocabulary. A reasoner query based on FOAF will now be able to return results even though the data was originally not described with FOAF.


* What can we use this for?
- Data integration: eg. multiple datasources using schemaX:classX (with its own rdfs:subClassOf foaf:Person) can be combined into 1 'FOAF'query across both datasets without manual mapping. This also enables query re-use.

- Interoperability: a third party querying our data using FOAF doesn't need to know our own vocabulary, they only need to understand FOAF

- automatical data enrichment: one could setup an ontology that automatically generates/derives additional information that can be used for other purposes. In this way it could also bring insights that would otherwise might not be (easily)discovered.

- data validation: with a correct description and rules one could validate datasets and check if they are well-constructed, complete, ... towards a target vocabulary.
