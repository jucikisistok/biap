# Chapter 6

### Part I: Whales, porpoises and the mammalian phylogenetic tree

I used the following sequences:  
Rat: https://www.ncbi.nlm.nih.gov/nuccore/NM_017120.3  
Camel: https://www.ncbi.nlm.nih.gov/nuccore/NM_001303563.1  
Dog: https://www.ncbi.nlm.nih.gov/nuccore/NM_001003086.1  
Whale: https://www.ncbi.nlm.nih.gov/nuccore/330688735  
Porpoise: https://www.ncbi.nlm.nih.gov/nuccore/330688731   
Hippo: https://www.ncbi.nlm.nih.gov/nuccore/U53901   
Giraffe: https://www.ncbi.nlm.nih.gov/nuccore/U53897   
Horse: https://www.ncbi.nlm.nih.gov/nuccore/NM_001081852   

Make sure to only retrieve the CDS as we need a conserved sequence to align and estimate the molecular clock.

![First tree](https://github.com/jucikisistok/biap/blob/master/figures/tree1.png)  

- *How many terminal nodes are there in your mammalian phylogenetic tree? How many internal nodes?*  
There are 5 terminal nodes and 4 internal nodes (shown by grey dots). 

- *Which node represents the most recent common ancestor of whales and any terrestrial mammal?*   
The node I labeled with C – it is the most recent common ancestor that wales have in common with a land mammal (camel). 

- *Which sequence was used as the outgroup to root the tree as it is shown in phylogram view?*  
The rat sequence.

- *Notice that the whale and dolphin branches aren’t equally long (in phylogram view). What do you think this difference in length represents, biologically?*  
After they diverged from their most recent common ancestor (D), they didn’t evolve at the same rate over evolutionary time. The whale sequence accumulated more changes / mutations, hence the longer branch length.

- *We have grouped the whales and dolphins with the herbivores but still have not answered the question posed at the start of the chapter about which terrestrial mammals are most closely related to them. Download sequences of the beta-casein gene for more herbivores and use phylogeny.fr to explore this question further. Camels, hippos (Hippopotamus amphibious; U53901), giraffes (Giraffa camelopardalis; U53897) and horses (Equus caballus; NM_001081852) would make good representatives of some major herbivore groups. How should whales and dolphins be grouped? Which land mammal is their closest relative? Are they still more closely related to each other than to any of the land mammals you have examined?*  
We get this tree:
![Second tree](https://github.com/jucikisistok/biap/blob/master/figures/tree2.png)  
 
We can see that whales and porpoises are still with the herbivores, because all herbivores (except horses) form a tight cluster. Horses appear more closely related to the carnivore group. Based on this tree, porpoises and whales are more closely related to hippos than to camels or giraffes. They still form their own branch, which suggests that their ancestor branched off from the land mammals prior to the separation of whales from porpoises.

### Part II: Evolutionary distance in the Mammalian Phylogenetic Tree

- *Using the Jukes-Cantor model, which sequence is most similar to the whale sequence? Which is least similar? Do these results agree with the results you obtained from phylogeny.fr?*  
Whales are the closest to porpoises and the most distant from rats, which is in agreement with the phylogenetic tree. If we only consider the herbivores, whales are most distant from horses.
![Jukes-Cantor model](https://github.com/jucikisistok/biap/blob/master/figures/jc.png)  

- *How do the distances change if you use the Kimura model? Based on what you observed for these particular sequences, how important is it to take the transition bias into account?*  
We get pretty similar distances, although the Kimura distance estimates are slightly larger, which is especially noticeable as the distances increase. The tree wouldn’t change, however, taking the transition bias into account would indeed yield potentially meaningful changes in absolute distances.
![Kimura model](https://github.com/jucikisistok/biap/blob/master/figures/kimura.png)  

- *How do the distances change if you use the Tamura model? Do the distances remain proportional even if the absolute numbers change? Do you think G+C bias was important for these sequences?*  
The Tamura model gives slightly smaller distances, however, the overall tendencies are the same and the tree wouldn’t change. However, we can see some considerable changes: for example, giraffes seem to be less similar to the other species using this model. This suggests that taking the GC bias into account may indeed be an important consideration.
![Tamura model](https://github.com/jucikisistok/biap/blob/master/figures/tamura.png)  

- *Choose one of the models and sketch a phylogenetic tree based on the distances your model calculated. Remember to make your branch lengths proportional to distance. Although we will see in Chapter 7 that tree-building programs use more sophisticated algorithms than this, assume in constructing your tree that the calculated distance is the distance from the tip of the branch belonging to species #1 to the tip of the branch belonging to species #2. How does your tree compare to the one generated by phylogeny.fr?*  
They should look similar to the tree above.

# Chapter 7
Coming soon.
