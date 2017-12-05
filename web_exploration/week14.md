# Chapter 11

### Part I: Exploring the structure of the HIV protease

**The HIV protease functions as a dimer. Some enzymes that form dimers then have two active sites. Is this the case for the HIV protease? Briefly describe the relationship of the active site and peptide-binding cleft to the subunits of the enzyme.**  
No – here the active site is the interface between the two subunits, so each subunit forms half of the pocket. 

**What kinds of amino acids do you find in the areas of the protein exposed to the water around it (e.g., when the protein is in solution in the cytoplasm)?**  
Hydrophilic ones.

**If you were to design an inhibitor of the HIV protease, where would you want it to bind? What kind of molecule might you use as the prototype to develop the structure of a good inhibitor?**  
A good idea would be to block the active site by binding an inhibitor, thus blocking the polymerase’s ability to bind a protein. A good template would be a peptide that could bind in the active site, however, we probably wouldn’t want to use a protein as our inhibitor due to proteins’ instability in the body.

**Using the cartoon or ribbon view, you should be able to identify where a long beta-strand on each subunit of the protease makes a hairpin turn, forming flexible flaps that cover the active site cleft. These flaps control access of the substrate to the active site. Which amino acids form the flaps (just give the range of numbers)? Although this region is very important to protease function, why are the flaps not likely to make a good target for rational drug design?**  
We can find the flaps around amino acids 42-58 on each subunit. It’s not a good target for a drug as it is fairly long and flexible, so it’s unlikely that binding something to it would significantly change the molecule shape.

**What are the numbers of the amino acids on each chain that form the Asp-Thr-Gly (Asn-Thr-Gly in this mutant) aspartate protease motif in 1KJF?**  
Asn: 25, Thr: 26, Gly: 27 on each subunit.

### Part II: Homology modelling of a mutant HIV protease

**How many mutations are there in the mutant protease sequence, as compared to the sequence of the protease you examined in Part I? Use pairwise alignment to find out.**  
I got this by aligning the mutant sequence with 1KJF in EMBOSS Needle – the number of differences is 13.

**In the regions you highlighted, how would you characterize the effect of the mutations on the structure of the protein, in general?**  
The original protease structure (red) fits the peptide substrate more tightly than the mutant structure (blue). The amino acid changes seem to have the effect of enlarging the binding pocket by bending regions near the active site outward.

**How do you think these structural changes would affect the binding of a small inhibitor molecule to the protease active site? Why do you think they have less effect on the binding of the natural substrate?**  
Since the binding pocket is enlarged, it’s less likely that an inhibitor molecule could bind tightly. This effect would apply to a natural peptide substrate as well, however, a larger substrate would likely fill the pocket better and would be more difficult to dislodge.

**If you wanted to design a drug that would inhibit this mutant protease, what characteristics would you want it to have?**  
It should have a shape that allows it to interact tightly with the altered regions of the mutant protein.

**Change the colors of your model so that everything is white except the three amino acids of the aspartyl protease motif (make the substrate gray for contrast). Make these three amino acids blue on the mutant chains, then see what happens when you color them red on the non-mutant chains. Does their position change in the mutant relative to the unmutated protein? Is this what you would expect? Certainly changes in the sequence or structure at these positions could lead to drug resistance; why then do we not observe them among drug-resistant HIV isolates?**  
These are key active-site amino acids (25-27 on all strands) – the protease will be non-functional if these are significantly displaced, hence, such variants are strongly selected against (therefore, we don’t observe drug-resistant variants that show large differences here).

### Part III: Predicting Secondary Structure from Amino-Acid Sequence 

**How well did PSIPRED predict the secondary structures in the HIV protease? Give specific examples of structures predicted accurately by PSIPRED, predictedstructures not found in the actual structure and actual structures that were not predicted.**  
It’s a very accurate prediction – nearly all of the structures found by PSPIRED were present in the crystal structure (including some very short beta-strands). There are some differences (eg. PSPIRED predicted an alpha-helix at amino acids 20-25 that is really a part of an adjacent beta-strand), but overall it’s a good de novo prediction.

**PSIPRED uses a prediction algorithm not unlike the Chou-Fasman algorithm we will use in the Programming Project. However, instead of applying its algorithm directly to your input sequence, it first does PSI-BLAST search to get a collection of sequences related to your input. It then applies its prediction algorithm to the results. Why might this method be advantageous in improving the program’s ability to identify genuine secondary structure?**  
If an amino acid is part of an actual secondary structure, like an alpha-helix, we expect that mutations that change this to an amino acid with poor alpha-helix potential would be selected against and amino acids with good alpha-helix potential would tend to be conserved at this position. By using a sequence comparison to look at conservation prior to predicting structures, PSIPRED can ‘filter out’ amino acids that don’t genuinely contribute to structures and thus improve its accuracy.

# Chapter 12

### Part I: Secondary structure in the LAT

**Does it appear that the LAT has significant secondary structure? Describe generally what the structures predicted by mfold look like and how extensive the base-pairing is.**  
Yes, very much so. 45 folded structures were returned by mfold, these are structures where the stabilities are above the cutoff value. We can see a long stem interrupted by some internal loops, bulges and stem-loop structures.

**How would you explain the fact that mfold found many possible structures, not just one optimal structure?**  
There is more than one way to fold a nucleic acid with essentially the same stability – and the number of possibilities scale fast when long sequences are considered. The algorithm used by mfold is a pretty sophisticated one (takes into account the contributions of the loops), and it aims to find all high-stability structures, not just the best one.

**Are the different structures predicted by mfold generally similar, or quite different?**  
They are very similar, but the arrangement of the bulges, loops and stem-loop structures is different.

**Most RNAs are not very stable in the cytoplasm of cells: they are quickly broken down by RNAses that attack single-stranded RNA (relatively rapid mRNA turnover is necessary in order for genes to be turned off effectively). The LAT, however, is a highly stable RNA. Does its structure provide any clues to this unusual stability?**  
Basepairs stabilize nucleic acids and we can see on the predictions that LAT seems to have so much basepairing that it’s essentially double-stranded, implying that it’s fairly stable.

### Part II: Designing PCR Primers to Amplify a Viral Gene 

**What is the initial result of the Web Primer analysis? Looking at your LAT intron sequence, can you see why this result was obtained?**  
The first result should be an error message indicating that no primers meeting the criteria set by the program parameters could be found, because the GC range was too stringent. If we look at the sequence, we can see that there is a high frequency of G’s and C’s. The error arises because the default is a maximum G+C percentage of 60% and there aren’t any 20-base sequences in the flanking DNA that have lower GC content than this.

**Use the information from 1. to decide how to adjust parameters appropriately to get a better result. What parameters did you have to change, and what values did you set?**  
We have to adjust the parameters under Primer composition – this is a trial-and-error exercise. If we ramp up the GC content, then we can find way too many primers, while making the parameters too strict can result in finding primers for one end but not the other (they are quite different in terms of GC content).   
Also, when we allow high GC content, we also need to allow higher temperature as GC base pairs are more stable and raise the melting temperature.
Example parameters: Optimal GC = 65, Minimum GC = 60, Maximum GC = 70, Maximum Tm = 65.

**What are the sequences (write them both from 5’ → 3’) of the best pair of primers found by Web Primer? How long a DNA fragment would they amplify?**  
Depends on your choice of parameters. With the parameters the book suggests I got TCCTCCTCCGCTTCCGCCT and CAGTACCCTCCTCCCTCCCT, amplifying 2048 bp of DNA.

**What are the melting temperatures of the two primers in the best primer pair? What would be a good annealing temperature for your PCR reaction?**  
For this pair, the Tm values are 63 and 55, so a melting temperature of 50◦C would be needed.   
These Tm values are a bit far apart so it might be worthwhile to go back and find a pair that would be closer.

**How much potential is there for secondary structure in the best primers? How much potential for inter-primer interaction? Do these numbers change significantly as you go down the list of less-optimal primer pairs?**  
This pair has self-annealing values of 8 and 12 and a pair-annealing value of 6 which suggests a moderately good potential for self-annealing, particularly in the second primer, but below the acceptable cutoff that we used.
There wasn’t too much variation in our list, because the program only reports primers above its acceptable cutoff. Sometimes you can find very low values for the best pair of primers and values that are not as good for some of the others.

**If you were actually going to do this PCR reaction, what concerns might you have about the primers chosen by Web Primer? If you look at the list of all primer pairs that meet your criteria, do you see any others that might help with these concerns?**  
The top primer pair is pretty far apart in melting temperature and it’s questionable whether we’d get the desired specificity using a 50◦C annealing temperature with one primer having a Tm of 63.
There are some pairs in the list that are a little closer together that might possibly work better – and in our list, these are no worse in terms of base-pairing potential.

### Part III: Predicting Genes Encoding Functional Small RNAs

**How many potential microRNA precursors were identified?**  
55

**Were there any similarities to known microRNAs that might strengthen the likelihood that these are genuine miRNAs?**  
No – we can get this piece of information at the bottom of the results page (Aligments with miRBase miRNAs: None).

**The HHV-1 and HHV-2 viruses are closely related and behave similarly with regard to infection and latency. We might expect that any genuine miRNAs in HHV-1’s LAT would also be found in the LAT of HHV-2. Use mirEval to identify potential miRNA precursors in the HHV-2 LAT; are there similarities that strengthen the case for authentic miRNAs?**  
This one can’t be answered, so just skip it and enjoy your day.
