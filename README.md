
# Approach
1. Python is used for data processing in this work. Pandas library is used to read the original data line by line through setting the chunk size to be equal to 1. Once a line is read, only data used in this project are extracted, if their are unmeaningful data or OTER_ID is not blank, the line will be dropped. If the line is not dropped, the ZIPCODE with 5 digits is extracted. Every valid line will then be stored in Data Frame C. 
2. In the nest step, it will be check whether the donor of this newly imported line is a repeat doner by searching the name and zipcode in data frame C. If it is a repeat donor, the CMTE_ID is extracted. By using the zipcode and CMTE_ID, the all transactions in the calendar year will be found in data frame C.
3. After finding all transactions of the repeat donor in the data frame, the transactions amount will be ceil to integer and put into numpy array. The total amount will be calculated. The percentile will then be calculated according to the definition in Wekipedia.

# file input/output

According to the requirement of the challenge, "percentile.txt" and "itcont.txt" are stored in "input" folder. Thus in the code, the parent folder of this file is firstlty searched using os library. As a consequence, the directory of the input files and output file can be generated. The results will be directly write to the output folder.

# library used

import pandas as pd
import numpy as np
import math
import os


