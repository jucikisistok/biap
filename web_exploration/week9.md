If you have any questions popping up while solving these exercises (be it a theoretical one or something practical about the web tools not giving you the answers you wanted), you can submit them to this board: https://trello.com/b/jrWFwod2/programming-bioinformatics  
This way we can collect the pain points easily and make sure that everyone is on the same page at the end of the day :) 

# Chapter 3

### Part 1: Pairwise global alignment with the Needleman-Wunsch algorithm

- *How many matching nucleotides are there between your two sequences? What is the alignment score?*   
Matching nucleotides: 1319  
Alignment score: 4934.5  

- *How many gaps were needed to align these sequences? Is there any particular pattern to where or how the gaps occur?*  
131 gaps were needed to align the sequences.  
Most gaps were appended to the beginning and end of the reference strain (A/California/07/2009), since it's a shorter sequence compared to A/Brisbane/59/2007. However, we can also find some gaps throughout the alignment.  

- *Can you suggest where the coding sequence might occur within this segment? What is your evidence?*  
The central region in the alignment has no gaps and we can find the start codon ATG at the beginning of this region, suggesting that the coding sequence might occur in this segment.

- *What is the logic behind the affine gap penalty, which imposes a large penalty for opening a new gap but a much smaller penalty for extending the size of an existing gap?*  
The idea is to prioritize the lengthtening of gaps over opening new small gaps throughout the alignment - this causes fewer breaks in the coding sequence and supports the knowledge that mutations are relatively rare (ie. a long sequence of gaps might be the result of one mutation, while several individual gaps suggest several mutations).

- *When you align the two HA sequences using a higher gap opening penalty, does the percent identity change significantly? How about the number of gaps and their placement and sizes?*  
The identity percentage doesn't change significantly (goes down by 0,6%). 
We have 81 gaps and the vast majority of them are at the beginning and end of the shorter sequence. We can only find one gap of length 3 within the sequence.

- *Your alignments with higher and lower gap opening penalties are both optimal alignments, and they have quite similar scores. Which alignment do you think is better biologically and what is your justification?*  
In the alignment with gap penalty of 50 we can only find one column of 3 gaps within the sequence, which might correspond to the deletion of one amino acid. This is less damaging to a protein sequence than multiple one and two nucleotide indels (which would correspond to frameshift mutations, a much more detrimental mutation type in terms of the protein). This suggests that the second alignment is biologically better.

- *Discuss how closely the HA segments of the two modern viruses are related to each other and how closely they resemble the 1918 virus. Can you draw any conclusions from your data about the origin of HA in the 2009 pandemic virus?*  
When aligning the 2009 California H1N1 and 2009 Brisbane H1N1, we got an alignment score of 4768 when using the gap penalty of 50. If we try to align the 1918 virus with the California and Brisbane strains, we get the scores 5707 and 6090, respecively. These good alignments and alignment scores suggest that the 1918 virus could have been the origin of HA in the 2009 pandemic virus.

- *If you were to use a different segment from the same viruses for your sequence comparisons, you might come up with different answers. How is this possible?*  
Segments can be mixed and matched during the assembly of progeny viruses because multiple viruses can infect one host cell. Hence, a single virus can be segments with different origins.

### Part 2: Local alignment with the Smith-Waterman Algorithm

- *How good are the scores and the percentage of sequence identity for this comparison? Why don’t these statistics tell the full story in this case?*  
We get sequence identity of 25,7% and score of 1077, which is not that good. This result might be due to the fact that the coding sequence M2 from Brisbane is pretty short compared to the DNA sequence for segment 7 from California, therefore, we see a lot of gaps in the beginning of the alignment. 

- *Suppose we only looked at the portion of the 2009 segment that actually aligned with the M2 coding region of the Brisbane strain. How would this change the percentage identity? Is this degree of similarity as high as you would expect for these related strains?*  
In this case we see a much higher identity percentage (around 70-80%, depending how you choose the region), meaning a greater degree of similarity. This is closer to the expected degree of relatedness.

*Using EMBOSS-WATER*
- *How does this alignment differ from the previous one? Is the percent identity, either for the whole alignment or just for the regions that actually match, significantly better than before?*  
We see a small aligned region at the beginning, a long gap, then another aligned region. The overall score is not much better, however, the aligned regions have very high similarity.

- *There is an obvious difference in how the subsequences of the M2 coding region align with the 2009 segment 7 sequence in the local alignment. Can you suggest a hypothesis for why the sequences align this way? (Hint: remember that the M2 sequence is the protein-coding sequence.) Based on your hypothesis, is the local alignment superior to the global alignment in terms of its ability to help us understand the viruses biologically?*    
This suggests that the M2 gene has two exons separated by an intron. Since we are able to observe this in this particular case, we can say that the local alignment is better in the biological sense as we were able to learn something about viruses.

### Part 3: Using alignment to investigate virulence
- *What are the scores and sequence identities for a comparison of the two avian viruses? Are the differences between the human isolate and the avian isolates greater than the differences among avian isolates?*  
The two avian viruses have a score of 8205 and they are 96% identical.  
Avian sequence 1 is 97,5% identical to the human isolate (score: 8575) and avian sequence 2 is 95,2% identical to the human isolate (score: 8286) - these differences are comparable to the differences between the two avian strains.

- *Based on your results (which of course are limited—it would be necessary to do many more comparisons in reality), do you think there is evidence that human adaptation is occurring in H5N1 viruses that might merit concern about human-to-human transmission in the near future?*  
Based on this data we can't say that H5N1 HA is changing exceptionally fast. It's likely that the human isolate is an avian strain that someone in close contact with birds was able to catch and not a developing human H5N1.
