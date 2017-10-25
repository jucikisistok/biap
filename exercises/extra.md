<h2>So, you are done with the mandatory exercises and want a challenge. Good.</h2>

<h3>Guided programming project from Chapter 2</h3>

Goal: identify the location of all mutations between two strings.

Input: two equal-length DNA sequences, representing nontemplate strands for protein coding regions in 5’ to 3’ orientation

Output: description and location of all mutations or a message indicating that the sequences are identical

Step 1: read in sequences, initialize variables and read in data

Step 2: Transcription

Step 3: Translation

Step 4: String comparison

Bonus:
-	Modify the program so that it can handle input sequences that contain:
    - Uppercase and lowercase characters
    - Characters that do not correspond to any nucleotide
-	Find a way to include the stop codon and represent a stop in your program when the stop codon is encountered
-	Modify the program so the user can choose whether to compare DNA sequences directly, translate them before comparing or both
-	Allow the user to input either the template or nontemplate strand in either 5’  3’ or 3’  5’ orientation
-	Modify the program so that it outputs a txt file with the results

<h3>Century from year</h3>
Write a function that computes the century, given the year.
The first century starts from year 1 and goes up to and including year 100, the second century spans from year 101 up to and including the year 200 and so on.

Some test cases:
The function should return 20 for 1905 and 17 for 1700.

<h3>Complementary DNA</h3>
Write a function that given a strand of DNA, computes the complementary sequence.

Yes, you need loops for this.

When you are done with that, you can also explore cases like:
- what happens if the input string contains characters that aren't letters (but numbers or weird stuff like #?!)? How do you deal with that?
- how do you deal with uppercase and lowercase characters?
- if the input string contains something other than the allowed characters (aka A, T, G or C), can you find a way to throw an error? 

<h3>Transcribing DNA</h3>
Write a function that given a DNA string, computes the transcribed RNA (which is formed by replacing all occurrences of "T" in the DNA to "U" in the RNA).

You can try exploring the cases mentioned in the previous exercise.
