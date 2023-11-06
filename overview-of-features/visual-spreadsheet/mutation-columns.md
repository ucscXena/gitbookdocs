---
description: More information about how we color mutation columns
---

# Coloring for Mutation Columns

Samples that have mutation data are white with a dot or line for the mutation for where the mutation falls in relation to the gene model at the top of the column. Mutation data is colored by the functional impact:

* Red - Deleterious
* Blue - Missense
* Orange - Splice site mutation
* Green - Silent
* Gray - Unknown

Samples for which there is no mutation data are gray with no dot or line, and are marked as 'null'.

### **More details for 'S**omatic mutation (SNP and INDEL)' datasets

**Red** --> Nonsense\_Mutation, frameshift\_variant, stop\_gained, splice\_acceptor\_variant, splice\_acceptor\_variant\&intron\_variant, splice\_donor\_variant, splice\_donor\_variant\&intron\_variant, Splice\_Site, Frame\_Shift\_Del, Frame\_Shift\_Ins

**Blue** --> splice\_region\_variant, splice\_region\_variant\&intron\_variant, missense, non\_coding\_exon\_variant, missense\_variant, Missense\_Mutation, exon\_variant, RNA, Indel, start\_lost, start\_gained, De\_novo\_Start\_OutOfFrame, Translation\_Start\_Site, De\_novo\_Start\_InFrame, stop\_lost, Nonstop\_Mutation, initiator\_codon\_variant, 5\_prime\_UTR\_premature\_start\_codon\_gain\_variant, disruptive\_inframe\_deletion, inframe\_deletion, inframe\_insertion, In\_Frame\_Del, In\_Frame\_Ins

**Green** --> synonymous\_variant, 5\_prime\_UTR\_variant, 3\_prime\_UTR\_variant, 5'Flank, 3'Flank, 3'UTR, 5'UTR, Silent, stop\_retained\_variant

**Orange** --> others, SV, upstream_gene_variant, downstream\_gene\_variant, intron\_variant, intergenic\_region

Note that we are case insensitive when we color for these terms.

**For the gene-level mutation datasets (Somatic gene-level non-silent mutation):**

**Red (=1)** --> indicates that a non-silent somatic mutation (nonsense, missense, frame-shif indels, splice site mutations, stop codon readthroughs, change of start codon, inframe indels) was identified in the protein coding region of a gene, or any mutation identified in a non-coding gene

**White (=0)** --> indicates that none of the above mutation calls were made in this gene for the specific sample

**Pink (=0.5)** --> some samples have two aliquots. In the event that in one aliquot a mutation was called and in the other no mutation was called, we assign a value of 0.5.

