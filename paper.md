
 
# PythoFragam: A Python-based Optimization Tool for DNA Fragment 

## Uzma* and Zahid Halim 
uzma@giki.edu.pk ,zahid.halim@giki.edu.pk
### Ghulam Ishaq Khan Institute of Engineering Sciences and Technology, Topi 
***
#### <b>Abstract
 
  
##### <b>Motivation: 
<h5 style="font-family:verdana;">Motivation</h5><p style="font-size:160%;"> <p style="text-align:center;"><p style="font-family:courier;">A python-based tool and allied algorithm is presented that addresses the optimization of DNA fragment assembly using overlap layout consensus approach. We overcome the problem of reconstructing the original DNA from the fragments. The work explores multiple possible solutions using an artificial intelligence method called the Restarting and Recentering Hybrid Genetic Algorithm (RRHGA). The fragments are ordered based on minimizing the number of contigs using Power-Aware Local Search (PALS) algorithm. The quality of the proposed solution improves through two objective functions.</p></p></p>
###### <b> Summary: A DNA fragment assembly based on the overlap layout consensus approach using the RRHGA is presented. The RRHGA utilize PALS as an evolutionary operator to order the fragment while minimizing the number of the contig. The proposed framework consists of two objectives: (a) maximizing the sum of the overlapping surface between the two adjacent fragments using the overlap score as a fitness value, and (b) minimizing the number of contigs by using the PALS as an evolutionary operator. The fitness value and the number of contigs are used as a comparison metric. To framework is evaluated on 25 benchmarks datasets.  
###### <b> Implementation and Availability: The framework and its associated tool is implemented using python as a programming language and the code is available at https://www.minrg.org/toolsanddata 
###### <b> Contact: uzma@giki.edu.pk 
  
  ***
 ###### <b> 1 Introduction
  
  The Overlap Layout Consensus (OLC) approach used for the DNA fragment assembly is gaining popularity due to it producing long reads through next-generation sequencing (Johnson et al., 2020). The proposed framework is base on the OLC approach. The challenging part of OLC is the layout part, the heuristic, and artificial intelligence methods used for the layout phase. The objective of the layout phase is to find the correct order of the fragments having maximum overlap score between adjacent fragments and, at the same time, have the minimum number of contigs. The approach in (Hughes et al., 2014) combines the Restarting and Recentering Genetic Algorithm (RRGA) with a heuristic for improving the validity of the layout phase. The fitness value is the sum of the overlap score between adjacent fragments. The combination of heuristic and metaheuristic in RRGA makes it important to consider for solving optimization tasks. The goal of the DNA Fragment Assembly (DFA) is to minimize the number of contigs while ordering the fragments. The Power-Aware Local Search (PALS) is a variation of heuristic approach, i.e., Lin’s 2-opt. A new hybrid algorithm is designed in (Hughes et al., 2016)  that combines the PALS with GA for optimization of the DNA fragment assembly. The RRGA is used in the past to escape the local optima. To optimize the initial solution, 2-opt heuristic of TSP is applied before using RRGA. In the past literature, hybrid algorithms are used for DNA fragment assembly. This proposal combines the heuristic with the artificial intelligence approach and uses the sum of overlap score between adjacent fragments as a fitness value. These methods cause premature convergence when used with the GA. The main limitation of these works is utilization of criteria (fitness value) for ordering the fragments. The present framework focus on these two objectives to best represent the DNA fragment assembly. Therefore, the proposed framework designs a hybrid algorithm that integrates the PALS with RRGA. 
###### <b> 2. Description
  Various DNA sequencing technology are available these days each having its pros and cons. The main issue with these sequencing technologies is that they do not keep the details about the individual reads. To achieve this goal of the DNA fragment assembly, the proposed solution focus on two objectives (1) maximizing sum of overlap score between the adjacent fragments and (2) minimizing the number of contigs. Fig. 1(a) represents the proposed framework. The first read of the DNA sequences is considered here as an initial solution. Afterwards, the 2-opt heuristic is utilized to optimize the initial solution before applying the metaheuristic. The RRGA uses the results obtained from 2-opt heuristic as an initial solution (i.e., Centre). The RRGA generates two types of representations based on transposition for the population, namely direct and indirect representations. The direct representation applies the transposition on the centre to produce the population Whereas, the indirect representation applies the transposition on the centre before evaluation of the fitness value. Once the population is generated based on transpositions, the partially mapped cross over and swap mutation are used as an evolutionary operator. The fitness value uses the sum of overlap scores between the adjacent fragments to achieve the first objective. Smith-Waterman, a local search algorithm, is employed here for the overlap score between the fragments. For the second objective, PALS is used as an evolutionary operator. The best solution (B-chrom) is obtained from the hybrid GA. If the B-chrom is better than the centre based on the fitness value, the number of transpositions is decreased by 5 % and the B-chrom replaces the centre. Afterwards, the whole process is iterated. However, if the B-chrom is not better than the centre, the transposition is decreased by 10% without changing the current solution and the process is repeated. The stopping criteria for the RRGA is set to 100 generations. The present framework is compared with four state-of-the-art approaches using 25 benchmark datasets.
  </table>
<table>
 <tr>
  <td rowspan="3">(a)<img src="https://user-images.githubusercontent.com/64734218/81034809-ba0d2280-8eb1-11ea-9c5e-25c08d294292.jpg"" border=3 height=600 width=600></img></td>
  <td>(b)<img src="https://user-images.githubusercontent.com/64734218/81037644-ee3a1080-8ebc-11ea-96df-8c118b9726f2.png"border=3 height=200 width=200></img></td>
  <td rowspan="3">(e)<img src="https://user-images.githubusercontent.com/64734218/81037881-a7004f80-8ebd-11ea-8369-54ecf184ea56.png"border=3 height=600 width=600></img></td>
 </tr> 
<tr>
 <td>(c)<img src="https://user-images.githubusercontent.com/64734218/81037821-7e785580-8ebd-11ea-8f0f-108e694e382d.png"border=3 height=200 width=200></img></td>
 </tr>
<tr>
  <td>(d)<img src="https://user-images.githubusercontent.com/64734218/81037854-918b2580-8ebd-11ea-8f99-2ac9531583b3.png"border=3 height=200 width=200></img></td>
 </tr>
 <tr>
 <td colspan="5">Fig. 1 Framework and key results (a) overall working of the toll, (a) Fragment optimized using 2-opt, (b) Optimization using PALS after GA execution,(c) swapping representation, (e)performance comparison with state-of-the-art methods;</td>
 </tr>
</table>
###### <b> 3. Usage Scenario
    This section demonstrates the ability of the framework. Three types of experiments are conducted, with and without force recentre approaches for both types of representations (i.e., direct and indirect), (a) the first experiment use the PALS as an evolutionary operator, (b) the second experiment applies PALS on the resultant best chromosome of the GA for optimization, and (c) the third experiment is conducted for swapping representation. These experiments use the sum of overlap score between adjacent fragments to gauge chromosome quality. The overlap score between fragment j and j+1 is shown in Eq. (1).
    
   ![Eq. 1](https://user-images.githubusercontent.com/64734218/81039005-3ce9a980-8ec1-11ea-809c-ec9efd09a7cb.png)(1)
   
   Fig 1 (b) show the results of the first set of experiments.  The second set of experiments repeat the first set of experiments, however, it does not use PALS as an evolutionary operator. Here, PALS is applied on the solution obtained from the GA (see Fig. 1(c)). The third set of experiments combine the first and second set of experiments using swap representation (Fig 1(d)). 
The experiments carried on the proposed tool shows that when PALS is used as an evolutionary operator, it performs better without force recentre for directed representation.  The RRGA performs better than other alternatives, therefore all experiments on RRHGA with and without force recentre are compared with RRGA. The comparisons with RRGA indicate that the proposed tool perform better in 80% cases. The conclusion of the experiments reveals that the proposed idea for the first set of experiment for direct representation without force recentre option performs better. The proposed framework is also compared with four existing algorithms, namely, RRGA variation for DNA fragment assembly, PALS, GA, and Hybrid GA (i.e., GA+PALS), as represented in Fig 1(d), where it yield better results. We conclude from the simulations that the first set of experiments performed better for direct representation without force recentre option. The comparison between the proposed and the four state-of-the-art methods was also performed using 25 benchmarks datasets (Fig. 1.(e)). The limitation of the existing work is that, at times, it consumes more execution time. In the future, we will focus on deep learning techniques to solve the problem of DFA more efficiently.   
    
###### <b> References 
  [Johnson,Richard S. "Assessing Protein Sequence Database Suitability Using De Novo Sequencing." *Molecular & Cellular Proteomics.* The American Society for Biochemistry and Molecular Biology. Date Published. Date Accessed.](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Assessing+protein+sequence+database+suitability+using+de+novo+sequencing.+Molecular+%26+Cellular+Proteomics&btnG=)
  


[Hughes,James Alexande. "Restarting and recentering genetic algorithm variations for DNA fragment assembly: The necessity of a multi-strategy approach." *Biosystems.* Science Direct. December 2016](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Hughes%2C+J.A.%2C+Houghten%2CS.%2C+%26+Ashlock%2CD.+%282016%29+Restarting+and+recentering+genetic+algorithm+variations+for+DNA+fragment+assembly%3A+The+necessity+of+a+multi-strategy+approach.+Biosystems%2C+150%2C+35-45.&btnG=)

[Hughes,James. Houghten,Sheridan.Mallén-Fullerton,Guillermo.Ashlock,Daniel."Recentering and Restarting Genetic Algorithm variations for DNA Fragment Assembly." Computational Intelligence in Bioinformatics and Computational Biology .  IEEE .  30 June 2014 .](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Hughes+J.%2C+Houghten%2CS.%2C+Mallen-Fullerton%2CG.M.+and+Ashlock%2CD.+%282014%29+Recentering+and+restarting+genetic+algorithm+variations+for+DNA+fragment+assembly.+In+IEEE+Conference+on+Computational+Intelligence+in+Bioinformatics+and+Computational+Biology%2C+1-8.&btnG=) 
