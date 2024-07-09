# 1.  Overview: 
The new perspective on salmon populations – required to address ecosystem based management and wide-scale impacts on salmon such as declining marine survival and hatchery effects – requires integrating salmon-related data from previously disparate field and lab sources with a myriad of habitat variables. Wider and deeper use of environmental and ecological data – to improve forecasts of salmon populations – will require a significant effort to coordinate, standardize, measure, manage, share, and analyze these indicators within and between cross-border agencies.

**The problem** is dataset interoperability (required to be FAIR). Without knowing the exact methods used to collect and process datasets, haphazard data integration will produce mistakes. This exact understanding of methods can only be achieved through transparent descriptions of what each method aims to achieve and how the resulting data should be interpreted.

**The solution** requires building a shared and machine accessible framework for discovering, standardizing, and managing the methods metadata for salmon datasets. This project delivers the tools and processes for this via collaboration between DFO, USGS (PNAMP), and PSMFC. Specifically, this project leverages (a) investments and experience behind the 1,359 rich descriptions of methods available in MonitoringResources.org and (b) design and technology for metadata management of Atlantic salmon datasets: the salmon ecosystem data hub,  SALHUB.
# 2. Process
Collaboration, _please._ [Claude 3.5](claude.ai) suggested the following steps, systematic and automated, as an approach. This process likely to evolve.

1. Data Preparation:
   - Ensure all 1,396 Method descriptions are in a consistent format, ideally plain text.
   - Organize them into a single corpus or database.
   - Quarto and R to extract, clean, compile as Google Sheet.

2. Automated Key Phrase Extraction:
   - Use Natural Language Processing (NLP) to extract key phrases.
   - (me starting with R code does not preclude Python: NLTK, spaCy, BERT,.)
   - Focus on noun phrases, as these are likely to represent important concepts.

3. Frequency Analysis:
   - Analyze the frequency of extracted phrases across all descriptions.
   - This will help identify the most common and potentially most important concepts.
   - A separate, parallel, project is applying AI based clustering of methods to derive important phrases.
     - That is top-down, this is bottom-up.

4. Domain-Specific Dictionary:
   - Create a dictionary of environmental science terms to improve accuracy.
   - This could be based on existing environmental science glossaries or taxonomies.
   - Current vague plan is automated ontology FROM methods (step 5), then human edits (step 6), then use that to improve automated ontology.

5. Hierarchical Clustering:
   - Use techniques like hierarchical agglomerative clustering to group similar terms.
   - This can help in forming the initial structure of the ontology.

6. Ontology Construction:
   - Start with high-level categories based on the main areas of environmental science (e.g., ecology, hydrology, atmospheric science).
   - Use the clustered terms to populate these categories and create subcategories.

7. Relationship Mapping:
   - Identify relationships between concepts (e.g., "is-a", "part-of", "used-in").
   - This could be done through co-occurrence analysis or more advanced NLP techniques.

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
