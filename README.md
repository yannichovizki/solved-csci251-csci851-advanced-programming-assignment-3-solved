Download Link: https://assignmentchef.com/product/solved-csci251-csci851-advanced-programming-assignment-3-solved
<br>
This assignment involves implementing a container to support some basic genetic related manipulations.

The genetic code is described in as a sequence of nucleotides or bases. Those bases describe our basic alphabet and for our standard genetics there are 4 bases in the alphabet.

<table width="401">

 <tbody>

  <tr>

   <td width="103">Base symbol</td>

   <td width="73">A</td>

   <td width="73">G</td>

   <td width="75">C</td>

   <td width="77">T</td>

  </tr>

  <tr>

   <td width="103">Base name</td>

   <td width="73">Adenine</td>

   <td width="73">Guanine</td>

   <td width="75">Cytosine</td>

   <td width="77">Thymine</td>

  </tr>

 </tbody>

</table>

Sequences of three bases, referred to as triplets or codons, map to amino acids. Chains of amino acids make proteins.

There are now attempts to develop non-standard genetics with synthetic bases and unnatural amino acids. Those would typically extend the base set but we are going to use a fictictious base set with only 3 bases in the alphabet.

<table width="295">

 <tbody>

  <tr>

   <td width="103">Base symbol</td>

   <td width="73">A</td>

   <td width="75">C</td>

   <td width="43">B</td>

  </tr>

  <tr>

   <td width="103">Base name</td>

   <td width="73">Adenine</td>

   <td width="75">Cytosine</td>

   <td width="43">Bob</td>

  </tr>

 </tbody>

</table>

To simplify processing we go to assume these also code to amino acids using sequences of 3 bases, which isn’t strictly necessary in nonstandard amino acids.

The provided data files, Codon3.txt and Codon4.txt, give example mappings between codons and amino acids &amp; instructions for the two different alphabets. The Start and Stop codons are instructions, not amino acids. They tell us when we begin and end a coding sequence. There will only be one line for each per file. The amino acids/instructions can generally have multiple codons that map to them.

You should only load the correspondence table once.

<h1>Classes: A container and two bases</h1>

You are to implement one container class template for storing an ordered list of objects associated with the nucleotides.

To avoid confusion with Base classes in the sense of inheritence I will refer to the classes for our symbols as being Alphabet classes. These classes store information about the symbols available, as in the tables above, and also information about the codons and their mapping to amino acids.

<ol>

 <li>AlphabetFour: The standard 4 base alphabet.</li>

 <li>AlphabetThree: The non–standard 3 base alphabet.</li>

</ol>

Each class should have the following functionality, although they can be organised differently:

<ol>

 <li>Loading the mapping between codons and amino acids from the data files. This should only be doneonce.</li>

 <li>Checking if the mapping covers all possible codons, so all possible combinations of 3 alphabet symbols.</li>

 <li>Mapping three elements from the alphabet, so a codon, to an amino acid or an instruction.</li>

</ol>

Your container should have the following functionality:

<ol>

 <li>Report on and validate the length of the container content. The length must be a multiple of 3.</li>

 <li>Report on the symbol distribution for the container.</li>

 <li>List the complete content of the container. This should display 60 elements per line, as in the sampledata files, GeneTest4-1.txt.</li>

 <li>Display all the encoded active amino acid chains. These means we read and process codons fromour data sequence, so symbols 3 at a time, until we reach a Start instruction. We then output the amino acids using the names seperated by dashes, until a Stop instruction is reached. The number of amino acids in each active amino acid chain should be reported. You then continue reading and processing codons as before.

  <ul>

   <li>If you are in an active sequence and reach the end of your data without reaching a Stopinstruction this should be reported.</li>

   <li>You also need to report the number of codons not displayed in between Stop and Start instructions, and at the beginning or end as appropriate.</li>

  </ul></li>

</ol>

The output based on the sequence processing should be something like the following:

5 codons read and ignored.

Sequence 1: Start-Phe-Lys-Stop. Contains 2 amino acids.

10 codons read and ignored.

Sequence 2: Start-Try-Asp-Ala-Pro-Pro-The-Iso-Stop.

Contains 7 amino acids. …

Note that other than for counting the symbols you only deal with them in blocks of three. So AATGCA is considered as AAT–GCA, not A-ATG-CA… with ATG being the Start symbol.

<h1>Genetics</h1>

Your code should compile on Banshee according to instructions you provide in a Readme.txt file. The program shold be named Genetics. The program should run as follows:

$ ./Genetics 3 Codons3.txt Datafile.txt $ ./Genetics 4 Codons4.txt Datafile.txt

where the 3 or 4 distinguishes whether we are dealing with an AlphabetThree case or an AlphabetFour case. That first value must be a 3 or 4. The Codons3.txt and Codons4.txt files could be named something else but will follow the codon to amino acid mapping files given. The file Datafile.txt will follow the structure of GeneTest3-1.txt and GeneTest4-1.txt and that’s the data you operate on.

<strong>So what do you do?</strong>

Based on 3 or 4 you get set up to deal with data of that type, so reading from the Codons3.txt or Codons4.txt type file specified as appropriate. Test and report on the validity of the table.

You then read from the provided data, into your container. Carry out the length validation and report on the length. Report on the distribution of symbols within your sequence. Print out the entire sequence. The display all of the encoded active amino acid chains.

The user shouldn’t need to give any input other than that given on the command line. If there is a problem with the data, so an invalid symbol or invalid Codons file, report the problem and abort.


