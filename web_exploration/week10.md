# Chapter 4
- *In their original survey, Salyers and colleagues used a cutoff of 95% identity for sequences considered similar enough to have been shared by HGT. You can get a quick measure of identity by using the max ident score in the BLAST results—however, you can also get a high max ident for a very small matched region, so also consider the query coverage. Looking at these parameters, are the matches that BLAST retrieved highly similar to your query, or less similar? Do your data suggest that all or most of them represent the same gene, transferred from organism to organism by HGT?*  
We can see in the list of top-matching sequences that they are extremely similar with high query coverage. These come from many different species, which suggests the horizontal gene transfer of the same gene rather than a common ancestor and mutation over a long period of time.

- *You may notice in your list that a number of the sequence matches come from cloning vectors—engineered DNA molecules used for laboratory manipulations. Construct an Entrez query to exclude these from your results and run your search again—but be careful not to exclude too much; remember that unless you limit the field, the entire text of each entry will be searched for a match. What query did you use?*  
We can use the query NOT vector [Title] – the [Title] part is important so that we don’t end up excluding results where the cloning vector is mentioned only in the text of the entry.

- *What evidence can you find among your BLAST results to support or refute the hypothesis that resistance genes are being shared between unrelated species—especially between agricultural species and human pathogens or human gut bacteria that might come into contact with pathogens? You will have to do some detective work to answer this question: for example, find a bacterial phylogenetic tree online to help you decide how closely related the different species in your list are, then try to find out which ones might be found in domestic animals, which are residents of the human gut and which are human pathogens.*  
If we look at the result list, we can see fairly unrelated bacteria (like Bacillus and Streptococcus, or Bacillus and Lactococcus). We can also see a number of human strains, a number of animal strains and some pathogens among the results. This suggests horizontal gene transfer between bacteria in agricultural animals and human gut residents. 

- *There are so many sequences in GenBank today, including many whole-genome sequences, that BLAST often fills up its list of top matching sequences without ever getting down to less related but potentially more interesting matches. In your initial BLAST results, for example, it's likely that most if not all of the sequences come from Gram-positive organisms, one major division of the bacteria. Horizontal gene transfer to the more distantly related Gram-negative organisms would be very interesting but is hard to assess from this list. Construct a BLAST search that excludes Gram-positive matches. Or, another way to get interesting results might be to require matches to specific groups of Gram-negative organisms that you know live in the human gut, such as Bacteroides (the most common genus among human gut bacteria) or Escherichia. Be careful to exclude from consideration sequences that come from cloning vectors in this case—you only want sequences naturally found in these bacteria. Describe how you searched, the similarity of your results to the query and whether the percent identity suggests that your results represent horizontally transferred genes or genes arising by mutation.*  
I limited my search to Bacteroides and Escherichia and the top results I obtained had Indent of 99%. The fact that we can see such high similarity in distantly related bacteria solidifies our belief that horizontal gene transfer indeed happened.

- *Based on your results thus far, would you say that you have evidence for (a) extensive horizontal gene transfer, (b) a mix of HGT and evolution by mutation, (c) evolution mostly by mutation with occasional HGT, or (d) a number of unrelated resistance genes? Support your answer with evidence.*   
As discussed above, there is evidence for extensive horizontal gene transfer (a). A mix of evolution and HGT (b) is also an appropriate answer -  if we investigate the BLAST results further, we can see that there are genes with strong similarity only in short regions as well as genes that are less similar, especially when we look at more distantly related algorithms. This indicates that evolution by mutation is also occurring, which is expected.

- *Which ermB-like genes are the most similar? Which are less similar? Are there particular regions of the gene that are highly conserved or less conserved?*   
This depends on which sequences you chose, but overall the sequences should be extremely similar along their whole lengths. We find differences in the Gram-negative bacteria, which would suggest an original Gram-positive to Gram-negative transfer that would have been followed by horizontal gene transfer within Gram-negatives. We can’t really see any well-defined more- or less-conserved domains among the highly related sequences, however, there are some genes among the BLAST results where only one region is in common with the query sequence. 

- *What kinds of differences can you see among these genes? Do substitutions outnumber indels, or vice-versa? What do you notice about the indels that occur in the alignment?*  
Substitutions greatly outnumber indels and we mostly see transitions (purine to purine or pyrimidine to pyrimidine, : A↔G or C↔T). Indels are rare (or you might not even see any, depending on your sequence choices). If you see indels, they are normally close to the ends of the sequences or they occur as three-nucleotide insertions or deletions that leave the reading frame undisrupted.

- *Try running ClustalW again with a very low gap penalty. Do the alignments change significantly? Which alignment do you think is more biologically relevant, and what is your evidence for this view?*  
Even if you set a pretty low gap penalty, ClustalW might not insert any gaps unless you’ve chosen some less-related sequences. If you have less-related sequences, then a low gap penalty might result in the insertion of more gaps and the tendency to scatter single gaps through the sequence as opposed to grouping them – this is likely to be less biologically relevant because it would lead to frameshift mutation which would greatly change the protein.

- *Based on the criterion of closely related genes from unrelated organisms, do your results support the horizontal gene transfer hypothesis?*  
There is strong evidence for horizontal gene transfer – the genes above 99% identical to the ermB gene are found in organisms like Bacillus, Clostridium and even the Gram-negative E.coli and Bacteroides, each of which are distantly related.

# Chapter 5

The book asks you to find out more about one or more candidate virulence genes – this is a very open question so you are free to explore, but here are some guidelines.  

**yadK**  
-	A gene that encodes a protein responsible for creating filaments / pili – bacteria use these to attach to surfaces (like the surface of the intestinal epithelium)
-	If a bacteria can’t attach to a surface, it will be washed out by the normal flow of material so better attachment helps bacteria to colonize and potentially cause disease

**yagW**

-	Encodes a receptor
-	No functions are yet known

**ybbK**  

-	Encodes a membrane-anchored protease
-	Surface proteases are important in pathogens in cleaving components of the matrix surrounding host cells, allowing the bacteria to move freely within the host tissues
-	It has similarity to a family of eukaryotic membrane proteins – we can speculate that it might form a tight contact with host cells, perhaps giving the protease access to some specific host target 

**ybgP**  

-	Encodes a protein matching a family of chaperones (assist in the folding of the proteins)
-	Proteins in this family assist the folding of the proteins that make up pili (important in attachment, keeping the bacteria anchored to the surface so that they can colonize)

**ycjZ**

-	Encodes a transcription regulator, binding to DNA to regulate the transcription of other genes
-	In other Gram-negative pathogens (eg. Salmonella, Vibrio cholerae) related proteins have been implicated in turning on virulence factors in response to conditions (eg. iron availability)
-	Possible function: allow the bacteria to turn on a set of genes when it is in a host and turn those genes off again when it is not

**ydgE**

-	Encodes a chaperone involved in transport of materials through the cell membrane
-	Orthologs have been implicated in export of drugs from the cell, leading to antibiotic resistance – might mean that E.coli expressing this gene will have higher levels of resistance (more likely to persist despite treatment)

**yeeJ**
-	Encodes a protein that has several copies of a domain similar to the “immunoglobulin fold” (Ig fold) - basic structural unit used in antibody proteins and other proteins of the mammalian immune system
-	Proteins with this structure are classified as intimins, proteins which bring bacteria into close contact with a host cell, and invasins, proteins which contribute to the ability of a bacterium to invade (enter) a host cell, which is part of the pathogenic mechanism for certain kinds of bacteria
-	It’s likely that these genes originate in horizontal gene transfer between prokaryotes and eukaryotes

**yehC**

-	Encodes chaperons that assist in the folding of the proteins that make up pili

**yhiF**

-	Encodes a response regulator protein
-	Bacteria very often sense external conditions by means of a two-component regulatory system: a sensor kinase protein located in the membrane binds some external signal molecule and then phosphorylates a response-regulator protein located in the cytoplasm - activated response regulator then binds DNA and either activates or represses transcription of a set of genes
-	Pathogenic bacteria might use such a system to sense whether they are inside or outside a host (or perhaps even inside or outside a cell, if it’s an invasive species) and turn genes on or off accordingly

**ysaS**
-	Orthologs of proteins encoded by this gene are components of Type III secretion systems
-	Type III secretion: the ability of many pathogenic bacteria to build a protein channel that connects their cytoplasm directly to the cytoplasm of the host cell
-	Receptor proteins are then moved through this channel that integrate into the host membrane and anchor the two cells tightly together
-	The pathogen can then move toxins or other proteins that affect host cell biology directly into the host cell
