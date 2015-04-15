# RAD-suckers
# This script will select loci with two alleles from STACKS "populations" program output file batch_X.haplotypes.tsv
# Commandline:
# python select_loci_with_two_alleles.py input_file output_file

import sys

input_file = open(sys.argv[1], 'r')
output_file = open)sys.argv[2], 'w')
header= True

# here is a for loop that will go line by line through your file
for line in input_file:

      # checking to see if this is the first line
      if header == True:
            output_file.write(line)
            header = False
      else:
            # counts the number of unique alleles, minus missing allele (-)
            alleles = line.replace('/', ' ') .split() [2:]
            unique_alleles =  list (set(alleles))
            if unique_alleles.sort[0] == '-':
                  unique_alleles = unique_alleles[1:]
              
            if len(unique_alleles) < 3:
                  output_file.write(line)
                  
input_file.close()
output_file.close()


# This script selects diagnostic loci between two population (fixed SNP markers within a population or species)

import sys

input_file = open(sys.argv[1], 'r'
output_file = open(sys.argv[2], 'w'
header = True

# here is a for loop that will go line by line through your file
for line in input_file:

      # checking to see if this is the first line
      if header == True:
            output_file.write(line)
            header = False
      else:
            total_ind = len(line.split() - 2
            
            # count the number of unique alleles in pop1
            pop1_alleles = line.split() [columnX:columnX]
            pop1_alleles_as_str = str(pop1_alleles).replace('[','').replace(']', '').replace("'", '').replace(',', '').replace('/', ' ')
            pop2_alleles_as_list = pop2_alleles_as_str.split()
            pop2_alleles_as_list.sort()
            if pop2_alleles_as_list[0] == '-':
                  pop2_alleles_as_list = pop2_alleles_as_list[1:]
            unique_alleles_pop2 = list(set(pop2_alleles_as_list))
            num_alleles_pop2 = len(unique_alleles_pop2)
            
            if num_alleles_pop1 == 1 and num_alleles_pop2 ==1:
                  if unique_alleles_pop1[0] != unique_alleles_pop2[0]:
                      output_file.write(line)
                      
input_file.close()
output_file.close()
            
