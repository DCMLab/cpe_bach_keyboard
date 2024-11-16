# annotation_workflow_template

This repo holds the current version of the DCML annotation workflow which is pulled by all subcorpus repos upon push to their main branch. 

Please note that the `meta_ corpora` branch should be used with collections of corpora.


## Overview
|file_name|measures|labels|standard| annotators  | reviewers  |
|---------|-------:|-----:|--------|-------------|------------|
|wq112n02 |      19|    38|2.3.0   |Amelia Brey  |DK          |
|wq112n08 |      12|    56|2.3.0   |Amelia Brey  |DK          |
|wq112n15 |      13|    28|        |Amelia Brey  |DK          |
|wq113n03 |       7|    29|2.3.0   |Amelia Brey  |DK          |
|wq114n07 |       4|     0|        |             |            |
|wq117n11 |      14|    35|2.3.0   |Amelia Brey  |DK          |
|wq117n12 |      14|    21|2.3.0   |Amelia Brey  |DK          |
|wq117n13 |       8|     0|        |             |            |
|wq117n14 |      18|     0|        |             |            |
|wq119n07 |     123|   340|2.3.0   |Amelia Brey  |DK          |
|wq50n01a |      48|   216|2.3.0   |Davor Krkljus|Victor Zheng|
|wq50n01b |      25|    42|2.3.0   |Davor Krkljus|Victor Zheng|
|wq50n01c |     166|   244|2.3.0   |Davor Krkljus|Victor Zheng|
|wq50n02a |     192|   340|2.3.0   |Davor Krkljus|ST          |
|wq50n02b |      31|    91|2.3.0   |Davor Krkljus|ST          |
|wq50n02c |     133|   215|2.3.0   |Davor Krkljus|Victor Zheng|
|wq50n03a |     192|   280|2.3.0   |Davor Krkljus|AB          |
|wq50n03b |      41|    88|2.3.0   |Davor Krkljus|AB          |
|wq50n03c |     100|   165|2.3.0   |Davor Krkljus|AB          |
|wq50n04a |     156|     0|        |             |            |
|wq50n04b |      17|     0|        |             |            |
|wq50n04c |     131|     0|        |             |            |
|wq50n05a |     104|   386|2.3.0   |Davor Krkljus|Victor Zheng|
|wq50n05b |      60|   114|2.3.0   |Davor Krkljus|Victor Zheng|
|wq50n05c |     229|   390|2.3.0   |Davor Krkljus|Victor Zheng|
|wq50n06  |     234|   450|2.3.0   |Davor Krkljus|AB          |
|wq55n01a |      69|    95|2.3.0   |Amelia Brey  |DK          |
|wq55n01b |      39|    58|2.3.0   |Amelia Brey  |DK          |
|wq55n01c |      44|    78|2.3.0   |Amelia Brey  |DK          |
|wq55n02a |      77|   167|2.3.0   |Amelia Brey  |DK          |
|wq55n02b |      49|   116|2.3.0   |Amelia Brey  |DK          |
|wq55n02c |     160|   163|2.3.0   |Amelia Brey  |DK          |
|wq55n03a |      42|    89|2.3.0   |Amelia Brey  |DK          |
|wq55n03b |      25|    41|2.3.0   |Amelia Brey  |DK          |
|wq55n03c |      68|   147|2.3.0   |Amelia Brey  |DK          |
|wq55n04a |     128|   314|2.3.0   |Davor Krkljus|AB          |
|wq55n04b |      32|   121|2.3.0   |Davor Krkljus|AB          |
|wq55n04c |     135|   266|2.3.0   |Davor Krkljus|AB          |
|wq55n05a |      29|   102|2.3.0   |Amelia Brey  |DK          |
|wq55n05b |      30|    64|2.3.0   |Amelia Brey  |DK          |
|wq55n05c |      37|    70|2.3.0   |Amelia Brey  |DK          |
|wq55n06a |      66|   229|2.3.0   |Davor Krkljus|AB          |
|wq55n06b |      30|    89|2.3.0   |Davor Krkljus|AB          |
|wq55n06c |     122|   202|2.3.0   |Davor Krkljus|AB          |
|wq56n01  |     176|   435|2.3.0   |Davor Krkljus|AB          |
|wq56n02a |      71|   164|2.3.0   |Davor Krkljus|Victor Zheng|
|wq56n02b |      24|    58|2.3.0   |Davor Krkljus|Victor Zheng|
|wq56n02c |      48|     0|        |             |            |
|wq56n03  |     149|   425|2.3.0   |Davor Krkljus|AB          |
|wq56n04a |      47|   161|2.3.0   |Davor Krkljus|AB          |
|wq56n04b |      73|   101|2.3.0   |Davor Krkljus|AB          |
|wq56n05  |     172|   308|2.3.0   |Davor Krkljus|AB          |
|wq56n06a |      41|    83|2.3.0   |Amelia Brey  |DK          |
|wq56n06b |      52|    90|2.3.0   |Amelia Brey  |DK          |
|wq57n01  |      94|   557|2.3.0   |Davor Krkljus|AB          |
|wq57n02a |      41|   116|2.3.0   |Amelia Brey  |DK          |
|wq57n02b |      32|    68|2.3.0   |Amelia Brey  |DK          |
|wq57n02c |      58|     0|        |             |            |
|wq57n03  |     141|   283|2.3.0   |             |AB          |
|wq57n04a |      81|   175|2.3.0   |Davor Krkljus|AB          |
|wq57n04b |      73|   166|2.3.0   |Davor Krkljus|AB          |
|wq57n04c |      52|    98|2.3.0   |Davor Krkljus|AB          |
|wq57n05  |     224|   366|2.3.0   |Davor Krkljus|AB          |
|wq57n06a |      90|     0|        |             |            |
|wq57n06b |      44|     0|        |             |            |
|wq57n06c |      70|   136|2.3.0   |Davor Krkljus|Victor Zheng|


*Overview table automatically updated using [ms3](https://johentsch.github.io/ms3/).*
