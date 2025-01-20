# Meta-impact: harnessing meta-analyses’ insights in ecology and evolution research

html file contains the analyses necessary to reproduce this research. Alternatively, one can check the rmd file for the code. Data is distributed in 3 csv files:

## `per_article.csv`

Each row contains information for a different article in the field of ecology and evolution published in 2023. 

### metadata
- `article_id`: unique identifier for articles in our dataset; open-ended text
- `article_doi`: article DOI; open-ended text
- `title`: article title; open-ended text
- `abstract`: article abstract; open-ended text
- `source_title`: name of the journal where the article was published; open-ended text
- `n_all_refs_lens`: number of references for each article according to the Lens database; numeric
- `n_all_refs_wos`: number of references for each article according to Web of Science (available only for manually inspected articles); numeric
- `n_meta_refs_auto`: number of meta-analytical references obtained through automated searches (i.e. using R); numeric
- `n_meta_refs_manual`: number of meta-analytical references obtained through manual inspections; numeric
- `manually_verified`: whether the article was manually inspected; restricted values: TRUE / FALSE
- `n_true_meta_refs`: number of true meta-analytical references (only available for manually inspected articles); numeric
- `n_false_meta_refs`: number of false meta-analytical references (only available for manually inspected articles); numeric
- `article_type`: our classification of article type (see Fig. 1 and Fig. S2)
- `jif_2022`: Clarivate's journal impact factor from 2022/2023; numeric
- `rel_all_meta_refs`: relative number of meta-analytical references from all references cited ; 
- `rel_true_meta_refs`:  relative number of true meta-analytical references from all references cited; numeric
- `rel_false_meta_refs`:  relative number of false meta-analytical references from all references cited; numeric

## `per_quote.csv`

Each row contains information for a quote (i.e. sentence) containing one or more meta-analytical references from manually inspected articles.

### metadata
- `meta_ref_id`: reference of the meta-analysis being cited; open-ended text
- `quote`: quote containing one or more meta-analytical references; open-ended text
- `reports_any_result`: whether the quote contains any result from the meta-analysis being cited; restricted values: TRUE / FALSE
- `reports_quantitative_result`: whether the quote contains a quantitative result from the meta-analysis being cited; restricted values: TRUE / FALSE
- `reports_limitation`: whether the quote contains a limitation from the meta-analysis being cited; restricted values: TRUE / FALSE

## `per_reference.csv`

Each row contains information for meta-analytical references from manually inspected articles.

### metadata
- `article_id`: unique identifier for the article from where the meta-analytical reference was extracted; open-ended text
- `meta_ref_id`: reference of the meta-analysis being cited; open-ended text
- `is_meta_ref_meta_analysis`: whether the meta-analytical reference is a true meta-analytical reference; restricted values: TRUE / FALSE
- `meta_ref_section`: the manuscript section where the meta-analytical reference was found; restricted values: introduction / methods / results / discussion/conclusion
- `meta_ref_section_adj`: the manuscript section where the meta-analytical reference was found but with fewer options; restricted values: introduction / methods / results/discussion/conclusion
- `meta_ref_quotes`: quotes extracted (separated by semi-colons when more than one occurred within the same manuscript sections); open-ended text