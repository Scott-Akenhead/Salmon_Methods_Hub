# 1.  Overview: 
The new perspective on salmon populations – required to address ecosystem based management and wide-scale impacts on salmon such as declining marine survival and hatchery effects – requires integrating salmon-related data from previously disparate field and lab sources with a myriad of habitat variables. Wider and deeper use of environmental and ecological data – to improve forecasts of salmon populations – will require a significant effort to coordinate, standardize, measure, manage, share, and analyze these indicators within and between cross-border agencies.

**The problem** is dataset interoperability (required to be FAIR). Without knowing the exact methods used to collect and process datasets, haphazard data integration will produce mistakes. This exact understanding of methods can only be achieved through transparent descriptions of what each method aims to achieve and how the resulting data should be interpreted.

**The solution** requires building a shared and machine accessible framework for discovering, standardizing, and managing the methods metadata for salmon datasets. This project delivers the tools and processes for this via collaboration between DFO, USGS (PNAMP), and PSMFC. Specifically, this project leverages (a) investments and experience behind the 1,396 rich descriptions of methods available in MonitoringResources.org and (b) design and technology for metadata management of Atlantic salmon datasets: the salmon ecosystem data hub,  SALHUB.
# 2. Process
Collaboration, _please._  
[Claude 3.5](claude.ai) suggested the following steps, systematic and automated, as an approach. This process likely to evolve.

1. Data Preparation:
   - Ensure all 1,396 Method descriptions are in a consistent format, ideally plain text.
   - Organize them into a single corpus or database.
   - Quarto and R to extract, clean, compile as strings vector. 

2.  Key Phrase Extraction:
   - Use Natural Language Processing (NLP) to extract key phrases.
   - (R in Quarto does not preclude Python: NLTK, spaCy, BERT,.)
   - Focus on noun phrases, as these are likely to represent important concepts.

3. Frequency Analysis:
   - Analyze the frequency of extracted phrases across all descriptions.
   - Identifying the most common phrases will help identify the most important concepts.
   - Fisheries and Oceans Canada has a parallel project: AI-derived clusters of methods to derive important phrases.

4. Domain-Specific Dictionary:
   - Create a dictionary of environmental science terms to improve accuracy.
   - This could be based on existing environmental science glossaries or taxonomies.
   - Current (vague) plan is automated ontology FROM methods (step 5), then human edits (step 6), then loop (step 4) to improve automated ontology.

5.  Clustering:
   - Try [hierarchical agglomerative clustering](https://en.wikipedia.org/wiki/Hierarchical_clustering) to group similar terms.
   - This can help in forming the initial structure of the ontology.

6. Ontology Construction:
   - Start with high-level categories, main areas of environmental science:ecology, hydrology, atmospheric science,.
     - The different view-points, the _facets,_ of our knowledge of salmon? [Multi-faceted classification](https://en.wikipedia.org/wiki/Faceted_classification).  
   - The clustered terms guide populating these categories; create subcategories.
   - Consider the drop-lists in a future User Interface: if each parent term has 15 child terms, 4 levels deep, then 15^4 = 50,625 terms. 

7. Relationships:
   - Identify links between concepts: -\[CONTAINS]->, -\[IS_AN_INSTANCE OF]->,.
   - Consider co-occurrence analysis, or advanced NLP I am unaware of.
   - End-users will evolve this; implies curators curb chaos.

8. Ontology Refinement; Validation and Iteration:
   - Use ontology editing tools like [Protégé](https://protege.stanford.edu/) to refine and visualize the ontology.
   - Have domain experts review the ontology for accuracy and completeness. Validation.
   - Iterate on the process, refining the ontology based on feedback.

9. Salmon Methods Hub:
    - **Implement the ontology in a graph database** for efficient querying and updating.
    - no discussion yet about extending to datasets, places, documents, people, agencies, taxonomy, ontology..
    - Goal upon attainment: Good UI/UX for end-users to add, edit, and **use** the methods.
      - Other processes will follow: best practices, best appropriate practices, standards for methods, official methods, versioning of evolving methods, sharing experiences with methods.  
# 3. Status
as of 2024-07-09: working on Step 1. Data Prep. Sheet with 1396 method names and URLs to methods descriptions. Quarto with R to extract, clean, compile.
