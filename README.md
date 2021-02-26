# FuzzyLogicRelationAlignment
FuzzyLogicRelationAlignment is a repository which contains:
- FuzzyLogic.jar - a java precompliled program to identify mappings between relations (object properties) of two OWL ontologies;
- ontology - a folder with ontologies, their mappings and relation semantic definitions
- fis - a folder with a configuration for fuzzy logic used for relation alignment 

Ontology folder contains:
- OWL ontologies (convention: ontology_name.owl)
- definition of relation semantics in the form of csv file (convention: ontology_name.csv)
- OWL ontologies' mappings in the form of rdf files (convention: ontology_name1-ontology_name2.rdf); 
Concept mappings are used as input for implemented algorithm for finding alignments between relation.
Relation mappings are used as benchmark data for implemented algorithm.
- OWL ontologies' mappings in the form of txt files, comming from LogMap (convention: ontology_name1-ontology_name2.txt);
Concept mappings are used as alternative input for implemented algorithm for finding alignments between relation.

To run the program
1. Download both folders (ontology and fis) and jar file in selected location
2. Being in that location open a console window and write:

   java -jar FuzzyLogic ontology_folder ontology1 ontology2 [-logMap]

e.g.

  java -jar FuzzyLogic ontology conference ekaw     // concept mapping comes from rdf file
or
  java -jar FuzzyLogic ontology conference ekaw -logMap   // concept mapping comes from txt file
  
 
It is assumed that:
-- java is visible (on the system path)
-- ontologies have owl extension (which is omitted)

The program produces a textual information about found mappings and their probability.
It also prints some basic measures (accuracy, precision, recall and f-measure) in referene to the benchmark.
