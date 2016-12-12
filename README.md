## RPD3
Mysql dump of curated pfam28 domains used for similarity search evaluation

This repository contains the Mysql database tables used to support the
analyses published in Pearson, Li, and Lopez (2016) Nuc. Acids
Res. "Query-seeded iterative sequence similarity searching improves
selectivity 5–20-fold" doi: 10.1093/nar/gkw1207.

The database consists of five tables taken from Pfam (pfam.xfam.org)
release 27, and another 3 tables that describe the subset of pfam
domains that met the RPD3 criteria of model-length and phylogenetic
diversity.

table | origin/description
------|-------------------
RPD3_domain_xref | auto_pfamA_reg_full for the 339 RPD3 domains/clans in RPD3 sequences
RPD3_pfamA | the domain/clan relationships for the pfamA domains in RPD3
RPD3_pfamA_joined_split |  not used
------|-------------------
clan | pfam27 (clans for all RPD3 domains)
clan_membership | pfam27
pfamA | pfam27 (all RPD3 domains contained in RPD3 sequences)
pfamA_reg_full_significant | pfam27 (domain annotations for RPD3 sequences)
pfamseq | pfam27  (RPD3 selected sequences)
pfamseq | pfam27  (RPD3 selected sequences)

Because of file size constraintsthe pfamseq table must be loaded from
multiple files.  The table can first be created using pfamseq.sql, and
then populated using the commands:

`load data local infile "pfamseq.txt.part_aa" into table pfamseq;`
`load data local infile "pfamseq.txt.part_ab" into table pfamseq;`
`load data local infile "pfamseq.txt.part_ac" into table pfamseq;`



