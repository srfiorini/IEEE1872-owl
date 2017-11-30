# IEEE1872-owl

IEEE1872-owl is an OWL specification of the Core Ontology for Robotics and Automation (CORA) and other ontologies in IEEE 1872-2015 standard.

# Included ontologies

We modularized the ontologies in different levels of axiomatization. The ontologies are:

* cora-bare.owl: A standalone taxonomy of the concepts and properties in CORA, without links to SUMO or CORAX.
* sumo-cora.owl: The taxonomy of concepts of SUMO used in the remaining ontologies.
* cora.owl: It is cora-base linked to sumo-cora, rparts and corax. This is the recommended implementation in this library.
* cora-fullaxiom.owl: A version of cora.owl + pos.owl with the result of our best effort to translate SUO-KIF axioms in SUMO and IEEE 1872-2015 to OWL. Use this implementation with care. 
* corax.owl: The OWL implementation of CORAX.
* rparts.owl: The OWL implementation of RPARTS.
* pos.owl: The OWL implementation of POS.
* annotation.owl: Some annotation properties for the ontologies in this project.

# Access

All ontologies can be accessed through the "http://purl.org/ieee1872-owl" prefix:

* http://purl.org/ieee1872-owl/cora-bare
* http://purl.org/ieee1872-owl/sumo-cora
* http://purl.org/ieee1872-owl/cora
* http://purl.org/ieee1872-owl/cora-fullaxiom
* http://purl.org/ieee1872-owl/corax
* http://purl.org/ieee1872-owl/rparts
* http://purl.org/ieee1872-owl/pos
* http://purl.org/ieee1872-owl/annotation

# Method for cora.owl

The translation from the specification in IEEE 1872 to IEEE1872-owl was made manually. We did not use any automatic translation tools. We tried to keep as maximum as possible the original ontological commitments of IEEE 1872. It is under-specified in relation to the SUO-KIF implementation. Consequently, IEEE1872-owl allows models that are not consistent with IEEE 1872.

In general, we used the following rules:

* SUO-KIF concepts were translated to OWL classes.
* SUO-KIF binary relations were translated to OWL properties, taking into account their meta-properties (asymmetric, reflexive, etc.) and their domain and ranges where possible.
* SUO-KIF class and relation taxonomies have been translated to the equivalent in OWL.
* SUO-KIF partitions have been translated to class disjointness unions over OWL classes.

# Method for pos.owl

The POS ontology include many ternary and one quaternary relation, as well as functions. Since these cannot be represented natively in OWL, we devised a reification method to represent them. More info can be found in the documentation of the classes \_Relation and \_Function in POS.

# Method for cora-fullaxiom.owl

Similar to cora.owl and pos.owl, adding:

* SUO-KIF axioms in SUMO having the form "Concept(x) -> formula" were translated as subclass restrictions. Some have been ignored for being too specific (such as the restriction that Objects must be mono or polychromatic) or being impractical\\impossible to represented in OWL. 

* SUO-KIF axioms in SUMO NOT having the form "Concept(x) -> formula" were avoided. We translated some of them if they: (a) are not too specific; or (b) do not force the inclusion of too many entities in the OWL ontology.

* SUO-KIF axioms in IEEE 1872-2015 were translated as subclass restrictions. It was not possible to translate some of them. All axioms have been annotated with cross-references to axioms in IEEE 1872-2015. See annotation property "IEEE 1872-2015 axiom code" for more info.

# Copyright

The IEEE 1872-2015 copyright is property of IEEE Standards Association. 

The OWL implementation of the ontologies in IEEE1872-owl are CC-BY-4.0 (https://creativecommons.org/licenses/by/4.0/)

# Collaborators

* Sandro Rama Fiorini (Lissi, UPEC, France)
* Vitor Fortes Rey (DFKI, TU-Kaiserslautern, Germany)

The first version was developed at Φ-Robotics Research Group (http://www.inf.ufrgs.br/phi-group/) at UFRGS, Brazil.

# Bibliography

* IEEE Standard Ontologies for Robotics and Automation," in IEEE Std 1872-2015 , 2015.
* Schlenoff, Craig, Edson Prestes, Raj Madhavan, Paulo Goncalves, Howard Li, Stephen Balakirsky, Thomas Kramer, and Emilio Miguelanez. "An IEEE standard ontology for robotics and automation." In Intelligent Robots and Systems (IROS), 2012 IEEE/RSJ International Conference on, pp. 1337-1342. IEEE, 2012, https://doi.org/10.1109/IROS.2012.6385518.
* Edson Prestes, Joel Luis Carbonera, Sandro Rama Fiorini, Vitor A. M. Jorge, Mara Abel, Raj Madhavan, Angela Locoro, Paulo Goncalves, Marcos E. Barreto, Maki Habib, Abdelghani Chibani, Sébastien Gérard, Yacine Amirat, Craig Schlenoff, "Towards a core ontology for robotics and automation", In Robotics and Autonomous Systems, Volume 61, Issue 11, 2013, Pages 1193-1204, ISSN 0921-8890, https://doi.org/10.1016/j.robot.2013.04.005.
* Carbonera, J.L., Fiorini, S.R., Prestes, E., Jorge, V.A., Abel, M., Madhavan, R., Locoro, A., Goncalves, P., Haidegger, T., Barreto, M.E. and Schlenoff, C., 2013, November. Defining positioning in a core ontology for robotics. In Intelligent Robots and Systems (IROS), 2013 IEEE/RSJ International Conference on (pp. 1867-1872). https://doi.org/10.1109/IROS.2013.6696603
* Sandro Rama Fiorini, Joel Luis Carbonera, Paulo Gonçalves, Vitor A.M. Jorge, Vítor Fortes Rey, Tamás Haidegger, Mara Abel, Signe A. Redfield, Stephen Balakirsky, Veera Ragavan, Howard Li, Craig Schlenoff, Edson Prestes, "Extensions to the core ontology for robotics and automation", In Robotics and Computer-Integrated Manufacturing, Volume 33, 2015, Pages 3-11, ISSN 0736-5845, https://doi.org/10.1016/j.rcim.2014.08.004.
* Vitor A.M. Jorge, Vitor F. Rey, Renan Maffei, Sandro Rama Fiorini, Joel Luis Carbonera, Flora Branchi, João P. Meireles, Guilherme S. Franco, Flávia Farina, Tatiana S. da Silva, Mariana Kolberg, Mara Abel, Edson Prestes, "Exploring the IEEE ontology for robotics and automation for heterogeneous agent interaction", In Robotics and Computer-Integrated Manufacturing, Volume 33, 2015, Pages 12-20, ISSN 0736-5845, https://doi.org/10.1016/j.rcim.2014.08.005.

