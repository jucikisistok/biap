# Chapter 9

### Part I: Sequence-based ORF identification using the NCBI ORF finder  

The sequence is 17510 bases long and with the default parameters we can find 98 ORFs. The top 10 longest are: 19, 4, 71, 39, 33, 32, 48, 9, 45, 18.
If we re-run the analysis and only list ORFs that are longer than 300 nucleotides, then we only find 19 ORFs.

I did the analysis with the default parameters and smartBLAST.

![ORF Finder](https://github.com/jucikisistok/biap/blob/master/figures/orffinder.png)  
*ORF Finder's output*  

**ORF19**
-	Frame 2, Strand +, 1478-2572
-	MULTISPECIES: VanA-type vancomycin resistance histidine kinase VanS

**ORF4**
-	Frame 1, Strand +, 3748-4779
-	Vancomycin/teicoplanin A-type resistance protein VanA [Enterococcus faecium]

**ORF71**
-	Frame 1, Strand -, 12001-10988
-	transposase [Enterococcus faecium BM4538]

**ORF39**
-	Frame 3, Strand +, 2787-3755
-	vancomycin resistance protein VanH [Enterococcus faecium]

**ORF33**
-	Frame 2, Strand +, 14900-15808
-	aminoglycoside nucleotidyltransferase ANT6 [Enterococcus faecalis]

**ORF32**
-	Frame 2, Strand +, 13283-14152
-	DNA polymerase [Staphylococcus aureus]

**ORF48**
-	Frame 3, Strand +, 16440-17234
-	APH(3') family aminoglycoside O-phosphotransferase, Bacteria [Staphylococcus epidermidis]

**ORF9**
-	Frame 1, Strand +, 7963-8700
-	23S rRNA (adenine(2058)-N(6))-methyltransferase Erm(B) [Streptococcus agalactiae]

**ORF45**
-	Frame 3, Strand +, 14133-14867
-	MULTISPECIES: class I SAM-dependent methyltransferase [Enterococcus]

**ORF18**
-	Frame 2, Strand -, 746-1441
-	MULTISPECIES: VanA-type vancomycin resistance DNA-binding response regulator VanR [Bacilli]

### PART II: Sequence-Based ORF Identification Using NEBcutter

![NEBCutter](https://github.com/jucikisistok/biap/blob/master/figures/nebcutter.png)  
*NEBCutter's output (after editing ORF names)*  

**A**
-	364 aa, coding region: 1478…2572
-	MULTISPECIES: VanA-type vancomycin resistance histidine kinase VanS [Bacilli]

**B**
-	343 aa, coding region: 3748…4779
-	Vancomycin/teicoplanin A-type resistance protein VanA (plasmid) [Enterococcus faecium]

**C**
-	337 aa, coding region: 10988…12001
-	ISL3 family transposase [Enterococcus faecium Aus0004]

**D**
-	322 aa, coding region: 2787…3755
-	MULTISPECIES: D-lactate dehydrogenase VanH-A [Bacilli]

**E**
-	302 aa, coding region: 14900…15808
-	MULTISPECIES: aminoglycoside nucleotidyltransferase ANT(6)-Ia [Bacteria]

**F**
-	300 aa, coding region: 10084…10986
-	IS3 family transposase, partial [Enterococcus faecium]
 
**G**
-	289 aa, coding region: 13283…14152
-	DNA polymerase [Staphylococcus aureus]

**H**
-	264 aa, coding region: 16440…17234
-	aminoglycoside O-phosphotransferase APH(3')-IIIa [Enterococcus faecium]

**I**
-	245 aa, coding region: 7963…8700
-	MULTISPECIES: 23S rRNA (adenine(2058)-N(6))-methyltransferase Erm(B) [Firmicutes]

**J**
-	244 aa, coding region: 14133…14867
-	MULTISPECIES: class I SAM-dependent methyltransferase [Bacteria]

**K**
-	231 aa, coding region: 746…1441
-	MULTISPECIES: VanA-type vancomycin resistance DNA-binding response regulator VanR [Bacilli]

**L**
-	228 aa, coding region: complement(6389…7075)
-	IS6-like element IS1216 family transposase [Listeria monocytogenes]

**M**
-	224 aa, coding region: 12234…12908
-	IS1182 transposase (plasmid) [Enterococcus faecium]

**N**
-	202 aa, coding region: 4785…5393
-	MULTISPECIES: D-Ala-D-Ala dipeptidase VanX-A [Terrabacteria group]

**O**
-	181 aa, coding region: 5821…6366
-	VanY-A/VanY-F/VanY-M family D-Ala-D-Ala carboxypeptidase [Enterococcus faecium]

**P**
-	176 aa, coding region: 15817…16347
-	MULTISPECIES: streptothricin N-acetyltransferase Sat4 [Bacilli]

**Q**
-	164 aa, coding region: 38…532
-	transposase [Enterococcus faecalis]

**R**
-	152 aa, coding region: complement(7404…7862)
-	hypothetical protein HMPREF1374_02349 [Enterococcus faecium P1190]

### Part III: Shine-Dalgarno Prediction and Codon Usage Analysis with EasyGene

![EasyGene](https://github.com/jucikisistok/biap/blob/master/figures/easygene.png)  
*EasyGene's output*  

**Does it seem like EasyGene ignores ORFs that lack Shine-Dalgarno sequences or that do not match codon usage data?**  
Seems like it – EasyGene only finds 15 ORFs while ORF Finder finds 98 using the default parameters. However, if we look carefully, some ORFs are the same – we can hypothesise that the others are not present in the EasyGene output because no Shine-Dalgarno sequence was found or they didn’t match the codon usage data.

**How does EasyGene’s list compare with ORF Finder’s when ORF Finder is limited to 100-amino-acid ORFs?**  
We can limit the search to 300 nucleotides which corresponds to 100 amino acids. With this length constraint, ORF finder finds 19 ORFs. 

**What if ORF Finder is allowed to find 30-amino-acid ORFs?**  
If we limit the search to 30 nucleotides (as this is the smallest we can get), it finds 223 ORFs, including a lot of very short ones.

**Does EasyGene identify any of the short ORFs excluded by the length limit as actual genes?**  
In the case of this sequence, the ORFs identified by EasyGene are relatively long.

**Does EasyGene fail to identify any genes that you annotated as genuine based on your ORF analysis and BLAST searches?**  
ORF39, ORF33 and ORF18 can’t be found in the EasyGene output, however, there is reason to believe that they are genuine genes.

**In EasyGene, what kind of start codons do you see? What happens if you click Alternative Initiation Codons in ORF Finder? Why is this result better, biologically?**  
ATG and TTG. If we run ORF Finder with a 300 nucleotide limit, then using the Alternative start codon setting it finds 23 ORFs instead of 19. As there can indeed be different start codons, allowing for this in ORF Finder models real-life biology better. 

**Why did EasyGene find the longer ORF instead of the shorter one with the more obvious start codon? Does BLAST confirm that this is a better result?**  
There can be multiple answers for this: either there wasn’t an identifiable Shine-Dalgarno sequence or the shorter ORF didn’t match the codon usage data. Without picking a particular ORF it’s hard to say whether it’s a better result, however, if we look at some of the short ORFs, we can see that they correspond to hypothetical proteins while the longer ORFs are already identified with a clearly defined function, so this can lead us to believe that this result is indeed better.
