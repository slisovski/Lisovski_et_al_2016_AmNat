# Appendix: Lisovski et al. 2016 American Naturalist

Original publication: http://www.journals.uchicago.edu/doi/10.1086/685282

## Details on the Individual-Based Model and Simulation Code

Details on the various steps involved in the simulation of the arrival and mating of the south polar skua population. To indicate which parts are modifications to the original model of Kokko et al. (2006), new steps are indicated in **bold**.In the model, the south polar skua population was initiated with N_m males and N_f females, BS brown skua females, and NrT territories with randomly distributed qualities (uniform distribution of integers between 1 and QT, where QT is maximum territory quality). The selection process is accelerated by choosing a high QT value; however, the final result is independent of the absolute difference between low- and high-quality territories (given that there is at least a difference of 
Each individual had allelic values a (females) and b (males) determining arrival, which was randomly chosen and uniformly distributed between 0 and 40.1. Start with d = 0 (day of arrival).2. Each south polar skua individual that has not arrived arrives if a random number, uniformly distributed between 0 and 1, falls below the threshold P(d,a)=(1 + exp[-2(d-a)])^-1 (if individuals are male) or P(d,b) = (1 + exp[-2(d-b)])^-1 (if female).3. Each south polar skua female that has arrived but that has not yet chosen an extra pair partner does so among the arrived south polar skua males.4. Each south polar skua individual that has arrived dies with probability e^beta*t. **Females and males become available again if they already had a mate and their mate dies.**5. **Arrived south polar skua males without a territory look for single brown skua females. The probability of a south polar skua male mating with a brown skua female is conditional on the number of available south polar skua females ( f1) and brown skua females ( f2) and equals P(f , f ) = (alpha/
2)^log0.5(f_2/(f_1+f_2)). Parameter a determines the mating behavior of south polar skua males; a = 1 means that south polar skua males do not discriminate either way, with a ! 1 indicating a disfavor for brown skua females and a 1 1 indicating a preference for brown skua females. Males may be left without territories if no brown skua females are available or if they choose to mate with conspecifics.**6. **Arrived south polar skua males without a territory are assigned to territories with unpaired south polar skua females. Males choose the best territories currently available. The order in which individuals are allowed to choose is random among arrived males. Some males may be left without a territory if no females are available.**7. **Newly arrived south polar skua males without a territory are assigned to empty territories. Males choose the best territories currently available. The order in which individuals are allowed to choose is random among newly arrived males. Some males may be left without a territory if no vacancies are available.**8. Newly arrived south polar skua females without a territory are assigned to territories occupied by unpaired territorial males. Females choose the best territories currently available. The order in which individuals are allowed to choose is random.9. **Newly arrived south polar skua females without a territory are assigned to empty territories. Females choose the best territories currently available. The order in which individuals are allowed to choose is random among newly arrived females. Some females may be left without a territory if no vacancies are available.**10. If d < 40, increase d by one time unit and repeat from step 2 onward.11. South polar skua breeding commences. Females who are on a territory produce offspring. The total number of offspring equals the quality of the territory. Offspring sex is randomly determined for each offspring independently (1∶1 primary sex ratio). Each offspring’s paternity is similarly independently determined: the probability that the sire is the extra pair male is p_E, and with probability 1-p_E the sire is the social mate of the female. Offspring inherit each allelic value randomly from either parent.12. **Mixed pair breeding commences. Brown skua females that are on a territory produce offspring. The ratio of offspring going into the south polar skua pool for the next year is determined by the parameter j (1 means that all hybrids inherit the allelic value of the south polar skua father, whereas 0 means that all hybrids inherit the allelic value of the brown skua mother). Offspring sex is randomly determined for each offspring independently (1∶1 primary sex ratio).**13. With a small probability mu, any allelic value a or b in an offspring mutates to a different uniformly distributed random value between 0 and 40.14. Autumn migration commences, vacating all territories. The winter population consists of parents and offspring of the previous summer. If there are more than N_f south polar skua females, a random subset is removed so that N_f are left; males are given the same treatment (ceiling, N_m).