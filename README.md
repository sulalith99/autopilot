# autopilot
# for Ag penta nanorod dimer systems

* autopilot calculates the excitations for Ag penta nanorod dimer systems using TD-DFTB methods. also, this bash script will remove layer by layer (six Ag atoms for a single layer) in a single nanorod up until half the length of the full nanorod, and create their coordinate files along with the input files.

* this will only handle one charge at a time.

* can also do the same type of calculations for the monomers as well; only need to change the path of the monomer coordinates.

* specified changing locations are highlighted in the script. Other than that feel free to change as needed.

* as the layers are removed one by one, one of the issues that we encountered is the HOMO and LUMO energies become degenerate (similar in energy) and the result is un-converged SFC cycles. therefore one of the best methods that can overcome this issue is using level shifting (shifting the LUMO energy by some specified energy). however, level shifting has not yet been implemented in the ADF TD-DFTB method; but it is possible to use in TD-DFT methods. another solution is to use "Fermi" instead of "Aufbau" as the strategy. even though it will solve the convergence issue, it will not continue the linear-response (LR) calculations due to fragment occupations. this indicates that the TD-DFTB calculations will limit most of the calculations that we were initially interested in (TD-DFT will be the possible solution but as the size of the system increases, computational cost will also increase rapidly).

* there are some calculations that will result in an error due to a different issue: the charge of the system is not correct. in these types of cases, we will be needing to go through several charges to find the most suited for the system. Therefore, the charge_finder script is introduced.
