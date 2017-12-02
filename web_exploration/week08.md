# Chapter 1

### Part 1  
**Examining the browser view & the rs11868035 SNP:**  
- *About how many nucleotides are displayed in this view?*    
501 basepairs

- *Find the ideogram - what is the position of the SNP?*  
17p11.2

- *Has this SNP been identified in more GWAS studies?*  
only the Do et. al. study according to the NFGRI Catalog track's entry

- *Does this SNP occur within a gene, and if so, what's the name of the gene?*  
There is no clear consensus here. Judging from the Human mRNA track, it's in the intron region (as thin lines represent introns), but if we look at the RefSeq track, it appears to be in a UTR. According to the Do et. al. paper, the SNP is within an intron.

- *Based on the Multiz Alignment track, would you say that the gene in which the rs11868035 SNP is found conserved? Is the specific sequence where this SNP occurs conserved? What animals might be appropriate model systems in which to conduct further research into the role of the gene is Parkinson Disease?    
The gene itself doesn’t seem very conserved, however, the specific sequence where the SNP can be found appears conserved. Rhesus might be a good model system.

- *Can you find any evidence that would suggest the possible involvement of a particular gene in Parkinson Disease?*  
**OMIM:** we find the SREBF1 (sterol regulatory element binding transcription factor 1), however, no associated OMIM phenotype map key info is available. We find RAI1 next to it, which is indeed a disease-causing gene, responsible for Potocki-Lupski Syndrome and Smith-Magenis Syndrome, both resulting in behavioural and cognitive manifestations   
**GNF Atlas 2:** we can see underexpressed genes in the nervous system which might be the result of a mutation.

**Investigate a second SNP: rs34637584.**
- *On which human chromosome is this SNP located and at what position?*  
The SNP occurs at position 12q12 (chromosome 12, long arm).  

- *Does it occur within a gene or between genes? If it occurs within a gene, is it within an exon or an intron?*  
It occurs on the LRRK2 gene, in the exon region.

- *Describe the alleles that occur through variation at this site.*  
We can see this if we click on the accession number in the NHGRI track. There are two variations – the wild type has a G, and the risk allele has an A. We can also see that the risk allele’s frequency is 0.002, which means that 0.2% of the alleles in the population are risk alleles.

- *List the genes found within approximately 500kb on either side of the SNP.*  
We can see this in the RefSeq track. To the left we find SLC2A13, and to the left we find MUC19 (however, its status is provisional at the moment). Next to MUC19, we find CNTN1.

- *Has this site or any of the nearby genes been associated with Parkinson Disease previously?*
We can examine the OMIM descriptions to find this information. The LRRK2 gene is associated with Parkinson Disease, but neither SLC2A13 nor MUC19 is associated with disease of any kind. CNTN1 is associated with congenital lethal myopathy, Compton-North type (some symptoms: hypertelorism, neonatal hypotonia and respiratory insufficiency due to muscle weakness.

- *What evidence did you find to support the identification of one or more of the genes in this region as a candidate for a PD-associated gene?*  
Based on the Atlas 2 track and expression studies, we can’t find very compelling evidence.

### Part 2

- *How long is the entire SREBF1 gene (in bp or kb)?*  
32663 bp according to the GenBank entry, 25663 bp according to the RefSeq track in the genome browser. Different experiments uncovered different exon combinations, hence the differences.

- *When you click on the CDS link in a GenBank entry, only short segments of the gene sequence are highlighted. What do these highlighted segments represent?*  
The exons. They are separated by introns before splicing.

- *How long is the spliced mRNA for SREBF1? What fraction of the gene is thrown away in the form of spliced-out introns?*  
We can find this piece of information by clicking on the mRNA link in the GenBank entry, get the mRNA in FASTA format, then do a character count – this way we find that the spliced mRNA is 5001 nucleotides long.

- *What accounts for the difference between the sequence segments that are highlighted when you click on the mRNA link versus when you click the CDS link?*  
The CDS only includes the coding sequence, while the mRNA includes untranslated regions and the coding sequence as well.

- *How long is the SREBF1 protein in amino acids? What are the first 10 amino acids in the protein sequence?*  
The SREBF1 protein is 1147 amino acids long – this was obtained by searching for the protein and doing a character count. The first 10 amino acids are MDEPPFSEAA.

- *What is known about the function of this gene?*  
It encodes a transcription factor that bind to the sterol regulatory element DNA sequence. It is involved in regulating genes involved in making sterols, the molecules that are made into steroid hormones and cholesterol.

- *Besides its hypothetical association with PD, what are two other known connections of SREBF1 to disease?*  
It’s not linked to any diseases in OMIM, but association studies link it to fatty liver disease, obesity and type 2 diabetes (this info can’t be found in OMIM directly though – click on MalaCards Disease Associations under the SREBF1 Description and Page Index, accessible from the OMIM page if you click on one of the Related USCS Gene(s)).

# Chapter 2  

- *What is the length of the CFTR gene? (make sure to retrieve the RefSeq entry from the Gene database)*  
188703 bp

- *Using the Range extractor to obtain the coding region of the mRNA*  
It should be Reading frame 1, 133-4572

- *Compare each of Mary’s alleles with the wild-type coding sequence. Can you identify a mutation in either or both?*  
A allele: G to A mutation at position 360  
B allele: G to A at position 1652  

- *Translate each of Mary’s alleles and compare them with the wild-type amino acid sequence. What differences can you detect?*  
A allele: no change, silent mutation  
B allele: G to D change at position 551 (Glycine to Aspartate)  

- *We know Mary is a carrier of the CF allele but does not have the disease. Summarize your findings for Mary’s CFTR alleles: describe the mutations that have occurred, discuss how (if at all) they affect the CFTR protein, and explain how your genomic data fits with what Mary already knows, including which allele she must have inherited from each of her parents.*  
Mary is a carrier, her A allele produces the wild type protein (she only has a silent mutation on that allele), but she has a mutation on the B allele that produces a change in the CFTR protein. Since we know that her mother has CF (meaning that she has two defective CFTR alleles), the B allele must be the one she inherited from her and the A allele must have come from her father. 

- *Repeat your analysis for each of Tom’s two alleles. Is he a carrier of CF? Summarize your findings as in the previous question and determine the probability that Tom and Mary will have a child with CF.*  
A allele: 3 nucleotide deletion at position 1521  
B allele: Wild type  
A allele after translation: F (phenylalanine) to gap at position 508  
B allele after translation: Wild type  
Both Tom and Mary are carriers, which means that their child has 50% chance of inheriting a mutant allele from each of the parents, hence, 25% chance that he/she will have CF.   
