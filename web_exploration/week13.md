# Chapter 10

### Part I: Gene prediction with GENSCAN and AUGUSTUS

Here is an example output with the explanation of the columns: http://globin.bx.psu.edu/dist/cathy/piptools.test/genscan.out 

**List the genes that GENSCAN found within the sequenced region, along with their lengths and the approximate length of the processed mRNAs. Why do the gene arrows point in different directions?**  
On the + strand, we find an exon of length 130 followed by a polyadenylation site. This could be an exon from a gene that begins in a sequence farther upstream.  
On the – strand, a multi-exon gene is predicted. We can see a polyadenylation site after the last exon and a promoter before the first exon. The length is 34680. The processed length is 3021.  
We find one more predicted gene on the + strand, we can see the promoter and the PolyA sites again. The length is 5859. The processed length is 738.  

**What is the difference between an exon marked Init and an exon marked Intr (in the text output)? Why is this difference significant in predicting genes?**  
Init is the predicted very first exon, starting with a start codon and Intr is an internal exon between the first and last exons. This is important because we can find exon-like sequences at random, but we can ignore them if they aren’t between a first and last exon.  

**Look at how the predicted proteins begin. Does this information strengthen or weaken the case for any of the genes?**  
Protein 2 and 3 start with M which should be the case since the start codon ATG codes for M. Protein 1 doesn’t start with M, however, it makes sense because it’s just a final exon from some gene that started in a sequence we don’t have.

**What other features did GENSCAN identify (look in the text output)? Do these provide additional support for any of the predicted genes?**  
It also predicts promoters and PolyA sites – these support that the predicted genes are genuine. The polyAsite is pretty far from the last predicted exon in Gene 3 and it’s also a bit far for Gene 2 – given its location, Gene 1 and Gene 2 mRNAs would overlap, so we should proceed with caution.

**How does the number of genes predicted by AUGUSTUS compare to the results from GENSCAN?**  
AUGUSTUS only finds one gene with two alternative transcript versions while GENSCAN found three distinct genes.

**How does the structure (e.g., length, number of introns and exons, position in the DNA) of the genes predicted by AUGUSTUS compare to GENSCAN?**  
Both find a long gene on the – strand. GENSCAN identifies 18 exons, while AUGUSTUS only identifies 14. It also finds a potential alternative first exon and constructs an alternative transcript with 12 exons. GENSCAN’s gene goes from position 13868 to 48538 and the transcripts identified by AUGUSTUS go from 13590 to 25048 (12 exons) and from 13590 to 48661 (14 exons).

**How do the predicted proteins compare? Clearly, they’re not identical, but do they appear related? For example, are they basically the same protein with perhaps some different splicing choices, or do they come from entirely different reading frames or even regions of the DNA? (You can of course use EMBOSS or BLAST to directly compare the proteins or their exons if you wish.)**  
For the long transcript the proteins are pretty similar but different splicing choices have been made.

**Describe the gene that you conclude may be important in influenza resistance: total length, number of exons, processed length, number of amino acids, etc.**  
There is room for interpretation here. In the absence of any further data we could argue for both transcripts, however, since there is a high GC content region within the longest intron that could imply a promoter region, we might want to go with the shorter transcript. In this case it has 12 exons (initial, terminal + 10 internal) and it goes from position 13590 to position 25048 (11450 bp long). The coding sequence is 1759 nt long and encodes a protein of 586 amino acids.

### Part II: Evidence of gene expression

Link to TSSG: http://linux1.softberry.com/berry.phtml?topic=tssg&group=programs&subgroup=promoter 

**Do the CpG islands within the sequenced region support your hypothesis about the genes that are found here? Do they provide any information that might help distinguish between the GENSCAN and AUGUSTUS results?**  
We can find CpG islands at the following positions: 31585 to 37639, 46530 to 46802, 69601 to 69862, 73372 to 73753 and 82306 to 82763. The one around 30k likely corresponds to the one that we observed in AUGUSTUS, which implies that indeed the shorter transcript might be the true one, since we can find the CpG island (which suggests the presence of a promoter region) before the start codon.

**Higher scores in the NNPP results mean putative promoters that better match the criteria. Note on your map where the strongest predicted promoters are. The large letters the predicted transcriptional start sites. Can you see good matches to the consensus TATA box sequence (tATAWAW) upstream of potential translational starts?**  
We get a huge amount of predicted potential promoter sites (all of them have pretty high scores too), plenty to support any gene that we’ve found so far, hence, this is not a very helpful result.

**How does the number of promoters returned by TSSG compare with the NNPP results? What else is different about the TSSG results, and how might this difference be useful?**  
We only get 18 promoters, the strongest ones being around 30k, which supports the hypothesis that the shorter AUGUSTUS transcript is the best one. It also returns the positions of potential TATA boxes and transcription-factor binding sites, further strengthening the validity of these promoters. There is some support for a promoter upstream of the longer transcript, however, the prediction is less strong in this case.

**Higher scores from TSSG again represent better promoter predictions. Do any of the high-scoring promoters match up (at least approximately) with high-scoring promoters from NNPP?**  
They match up pretty poorly. NNPP finds more promoters all around the genome, but the strongest TSSG promoters aren’t precisely found by NNPP.

**Does your expression analysis help to reconcile the differences between the GENSCAN and AUGUSTUS predictions?**   
Yes, there is evidence that AUGUSTUS’ shorter transcript is best because of reasons discussed above.

**Choose the gene you believe is founded on the most solid evidence, obtain its coding sequence, and use BLAST and OMIM to find out what is known about the gene. Have you actually identified a gene that makes sense in the context of influenza resistance?**  
BLAST finds a good match to Influenza virus NS1A-binding protein isoform X1, X2 and X4. These play a role in binding a key influenza virus protein, therefore, could potentially be involved in resistance to the virus. OMIM suggests a connection with the replication of the virus, so a mutation could potentially interfere with this process. 
