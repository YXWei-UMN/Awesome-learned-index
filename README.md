# Awesome-learned-index

This is a collection of learned index papers with notes.

## By year

### 2018

1. [2018-The case for learned index](papers/2018-google-learned-index.pdf): the first learned index paper. It introduces RMI that use tree-like structures. Inner nodes are models while leaf nodes are data. Each model maps from a key $k$ to a position $p$($k\rightarrow p$).

### 2019

1. [2019-SOSD_Benchmark](papers/2019-SOSD_Benchmark.pdf)

2. [2019-aiDM-Considerations_for_Updates](papers/2019-aiDM-Considerations_for_Updates.pdf): 
    1) major observation - when the insertions follow a different distribution than that of the base data, the error of the model grows linearly with the number of inserted items.  
    2) propose - segmenting and recording the error drift of each segment's starting key. Interpolating the drift of adjacent segments' starting key to get the drift of target key.

3. [2019-arxiv-Scalable_Learned_Index_in_Storage](papers/2019-arxiv-Scalable_Learned_Index_in_Storage.pdf):  
    1) the initial version of FINEdex, similar to FITing-Tree except insertion policy
    2) naive update (similar to chain-based hash collision) 

4. [2019-SIGMOD-FITing-Tree_Data-aware-Index](papers/2019-SIGMOD-FITing-Tree_Data-aware-Index.pdf)
    1) also by Tim Kraska
    2) use piece-wise linear function to approximate the mapping of key to location (memory-saving)
    3) greedy error-bound based segmenting strategy: greedy partition data (similar to Feasible space window), ensure each segment containing data with bounded error
    4) out-of-place insertion: buffering area within each segment, merge & re-segment once buffer is full
    5) <strong> diff between the tree and RMI, why 2-layer RMI is considered better </strong>
    6) other similar work: ASLM: Adaptive single layer model for learned index (multiple more complex greedy segmenting strategies)

### 2020

1. [2020-aiDM-Radix_Spline](papers/2020-aiDM-Radix_Spline.pdf): Using linear spine fits to a CDF, then a flat radix table as an appoximate index.
    1) spline interpolation based
3. [2020-APSys-SIndex_Scalable_Learned_Index__String_Keys](papers/2020-APSys-SIndex_Scalable_Learned_Index__String_Keys.pdf)
4. [2020-ICDEW-SMART-Self_Tuning_ART](papers/2020-ICDEW-SMART-Self_Tuning_ART.pdf)
5. [2020-OSDI-Bourbon_learned_LSM](papers/2020-OSDI-Bourbon_learned_LSM.pdf)
6. [2020-OSDI-Bourbon_learned_LSM_slides](papers/2020-OSDI-Bourbon_learned_LSM_slides.pdf)
7. [2020-PPoPP-XIndex_Scalable_Learned_Index_for_Multicore_Data_Storage](papers/2020-PPoPP-XIndex_Scalable_Learned_Index_for_Multicore_Data_Storage.pdf)
    1) Piece-wise linear model + out-of-place insertion 
    2) concurrency (w8 for further update)
9. [2020-SIGMOD-ALEX_Updatable_Adaptive_Learned_Index](2020-SIGMOD-ALEX_Updatable_Adaptive_Learned_Index.pdf)
    1) in-place insertion: reserve empty space for potential insertion. Collision is handled similar to hash linear probe
    2) exponential search instead of binary search <strong>(says it is because ALEX has better look up accuracy but why?)</strong>
    3) dynamic RMI, leaf node split once the empty space is less than a threshold
10. [2020-SIGMOD-CDFShop-Exploring_and_Optimizing_Learned_Index_Structures](papers/2020-SIGMOD-CDFShop-Exploring_and_Optimizing_Learned_Index_Structures.pdf): tuning parameters of RMIs
11. [2020-VLDB-PGM-index_fully-dynamic_compressed_worst-case_bounds](papers/2020-VLDB-PGM-index_fully-dynamic_compressed_worst-case_bounds.pdf)
    1) based on FITing-Tree (streaming segmenting <- greedy segmenting)
    2) LSM tree like insertion & deletion to delay and merge updates  <strong> any diff between insertion & deletion </strong>
    3) compression
12. [2020-workshop_NIPS_Learned_Index_for_bigtable](papers/2020-workshop_NIPS_Learned_Index_for_bigtable.pdf)
13. [2020-SIGMOD-HOPE](papers/2020-SIGMOD-HOPE.pdf): not learned index, but an encoding schme; order persevering encoding for string; can be used for string learned indexes
14. [2020-SIGMOD_The_Case_for_a_Learned_Sorting_Algorithm](papers/2020-SIGMOD_The_Case_for_a_Learned_Sorting_Algorithm.pdf)

### 2021

1. [2021-PVLDB-Benchmarking_Learned_Indexes](papers/2021-PVLDB-Benchmarking_Learned_Indexes.pdf)
2. [2021-AIDB-PLEX_RS+CHT](papers/2021-AIDB-PLEX_RS+CHT.pdf)
3. [2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing](papers/2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing.pdf)
4. [2021-PVLDB-FINEdex-Fine-grained_for_Scalable_Concurrent_Memory_Systems](papers/2021-PVLDB-FINEdex-Fine-grained_for_Scalable_Concurrent_Memory_Systems.pdf)
5. [2021-PVLDB-LIPP_Updatable_Learned_Index_Precise_Positions](papers/2021-PVLDB-LIPP_Updatable_Learned_Index_Precise_Positions.pdf)
6. [2021-aiDM-RUSLI_Real-time_Updatable_Spline_Learned_Index](papers/2021-aiDM-RUSLI_Real-time_Updatable_Spline_Learned_Index.pdf)
7. [2021-aiDM-Tailored_Regression_Learned_Indexes-Logarithmic-Error-Regression](papers/2021-aiDM-Tailored_Regression_Learned_Indexes-Logarithmic-Error-Regression.pdf)
8. [2021-PVLDB-Endownment-learned_cardition](papers/2021-PVLDB-Endownment-learned_cardition.pdf)

### 2022

1. [2022-PVLDB-are_updatable_learned_index_ready](papers/2022-PVLDB-are_updatable_learned_index_ready.pdf)
2. [2022-ICLR_learned_index_with_dynamic_eps](papers/2022-ICLR_learned_index_with_dynamic_eps.pdf)
3. [2022-VLDB-NFL_Learned_Index_Distribution_Transformation](papers/2022-VLDB-NFL_Learned_Index_Distribution_Transformation.pdf): it transforms keys distribution to make it more linear. [source code](https://github.com/luffy06/NFL)
4. [2022-TOS-Xindex-most-recent](papers/2022-TOS-Xindex-most-recent.pdf)
5. [2022-VLDB-APEX_Learned_Index_PM](papers/2022-VLDB-APEX_Learned_Index_PM.pdf)
6. [2022-learned_Similarity_Search](papers/2022-learned_Similarity_Search.pdf)
7. [2022-PVLDB-Endowment-FILM-for-Larger-than-Memory-Databases](papers/2022-PVLDB-Endowment-FILM-for-Larger-than-Memory-Databases.pdf)
8. [2022-PVLDB-Endowment-Can_Learned_Models_Replace_Hash_Functions](papers/2022-PVLDB-Endowment-Can_Learned_Models_Replace_Hash_Functions.pdf)

### 2023
1. [2023-FAST-ROLEX](papers/2023-FAST-ROLEX.pdf)
2. [2023-ASPLOS-LeaFTL- A Learning-Based Flash Translation Layer for Solid-State Drives](papers/2023-ASPLOS-LeaFTL-leared_FTL_for_SSD.pdf) Learned index for SSD FTL page-level memory mapping
3. [2023-PVLDB-Endowment-Comprehensive_Experimental_Evaluation](papers/2023-PVLDB-Endowment-Comprehensive_Experimental_Evaluation.pdf)
4. [2023-arxiv-Updatable_Learned_Indexes_Disk-Resident_DBMS](papers/2023-arxiv-Updatable_Learned_Indexes_Disk-Resident_DBMS.pdf)
5. [2023-arxiv-DILI-A Distribution-Driven Learned Index](papers/2023-arxiv-DILI-A%20Distribution-Driven%20Learned%20Index.pdf) Using more bulk loading time for better lookup.

## By category

### Survey/Benchmark/Tuning
1. [2019-SOSD_Benchmark](papers/2019-SOSD_Benchmark.pdf)
2. [2020-SIGMOD-demo-CDFShop-tuning_RMI](papers/2020-SIGMOD-demo-CDFShop-tuning_RMI.pdf)
3. [2021-PVLDB-Benchmarking_Learned_Indexes](papers/2021-PVLDB-Benchmarking_Learned_Indexes.pdf)
4. [2021-aiDM-Tailored_Regression_Learned_Indexes-Logarithmic-Error-Regression](papers/2021-aiDM-Tailored_Regression_Learned_Indexes-Logarithmic-Error-Regression.pdf)
5. [2022-are_updatable_learned_index_ready](papers/2022-are_updatable_learned_index_ready.pdf)
6. [2023-PVLDB-Endowment-Comprehensive_Experimental_Evaluation](papers/2023-PVLDB-Endowment-Comprehensive_Experimental_Evaluation.pdf)

### Read-only

1. [The case for learned index](papers/2018-google-learned-index.pdf)
2. [2020-aiDM-Radix_Spline](papers/2020-aiDM-Radix_Spline.pdf)
3. [2020-workshop_NIPS_Learned_Index_for_bigtable](papers/2020-workshop_NIPS_Learned_Index_for_bigtable.pdf)
4. [2021-AIDB-PLEX_RS+CHT](papers/2021-AIDB-PLEX_RS+CHT.pdf): RadixSpine as the top + Compact Hist-Tree as the bottom
5. [2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing](papers/2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing.pdf)

### Updatable

1. [2019-SIGMOD-FITing-Tree_Data-aware-Index](papers/2019-SIGMOD-FITing-Tree_Data-aware-Index.pdf)
2. [2020-SIGMOD-ALEX_Updatable_Adaptive_Learned_Index](papers/2020-SIGMOD-ALEX_Updatable_Adaptive_Learned_Index.pdf) Use gapped array for SMO
3. [2020-VLDB-PGM-index_fully-dynamic_compressed_worst-case_bounds](papers/2020-VLDB-PGM-index_fully-dynamic_compressed_worst-case_bounds.pdf)
4. [2021-PVLDB-LIPP_Updatable_Learned_Index_Precise_Positions](papers/2021-PVLDB-LIPP_Updatable_Learned_Index_Precise_Positions.pdf)
5. [2021-aiDM-RUSLI_Real-time_Updatable_Spline_Learned_Index](papers/2021-aiDM-RUSLI_Real-time_Updatable_Spline_Learned_Index.pdf)
6. [2022-TOS-Xindex-most-recent](papers/2022-TOS-Xindex-most-recent.pdf)
7. [2023-FAST-ROLEX](papers/2023-FAST-ROLEX.pdf)
8. [2023-arxiv-DILI-A Distribution-Driven Learned Index](papers/2023-arxiv-DILI-A%20Distribution-Driven%20Learned%20Index.pdf) Using more bulk loading time for better lookup.


### Secondary Storage/Persistent Memory/LSM

1. [2019-arxiv-Scalable_Learned_Index_in_Storage](papers/2019-arxiv-Scalable_Learned_Index_in_Storage.pdf): the initial version of FINEdex
2. [2020-workshop_NIPS_Learned_Index_for_bigtable](papers/2020-workshop_NIPS_Learned_Index_for_bigtable.pdf)
3. [2020-OSDI-Bourbon_learned_LSM](papers/2020-OSDI-Bourbon_learned_LSM.pdf)
4. [2020-OSDI-Bourbon_learned_LSM_slides](papers/2020-OSDI-Bourbon_learned_LSM_slides.pdf)
5. [2022-aiDM-LSI-Learned_Secondary_Index_Structure](papers/2022-aiDM-LSI-Learned_Secondary_Index_Structure.pdf)
6. [2022-VLDB-APEX_Learned_Index_PM](papers/2022-VLDB-APEX_Learned_Index_PM.pdf)
7. [2022-PVLDB-Endowment-FILM-for-Larger-than-Memory-Databases](papers/2022-PVLDB-Endowment-FILM-for-Larger-than-Memory-Databases.pdf)
8. [2023-arxiv-Updatable_Learned_Indexes_Disk-Resident_DBMS](papers/2023-arxiv-Updatable_Learned_Indexes_Disk-Resident_DBMS.pdf)

### Radix-Spine based

1. [2020-aiDM-Radix_Spline](papers/2020-aiDM-Radix_Spline.pdf): Using linear spine fits to a CDF, then a flat radix table as an appoximate index.
2. [2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing](papers/2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing.pdf)
3. [2021-AIDB-PLEX_RS+CHT](papers/2021-AIDB-PLEX_RS+CHT.pdf)
4. [2021-aiDM-RUSLI_Real-time_Updatable_Spline_Learned_Index](papers/2021-aiDM-RUSLI_Real-time_Updatable_Spline_Learned_Index.pdf)

### Variable length string keys

1. [2020-APSys-SIndex_Scalable_Learned_Index__String_Keys](papers/2020-APSys-SIndex_Scalable_Learned_Index__String_Keys.pdf)
2. [2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing](papers/2021-AIDB-RSS_Bounding_the_Last_Mile-Efficient_Learned_String_Indexing.pdf)
3. [2020-SIGMOD-HOPE](papers/2020-SIGMOD-HOPE.pdf): not learned index, but an encoding schme; order persevering encoding for string; can be used for string learned indexes
4. [2020-SIGMOD-HOPE_slides](papers/2020-SIGMOD-HOPE_slides.pdf)

### Concurrency

1. [2020-PPoPP-XIndex_Scalable_Learned_Index_for_Multicore_Data_Storage](papers/2020-PPoPP-XIndex_Scalable_Learned_Index_for_Multicore_Data_Storage.pdf)
2. [2020-APSys-SIndex_Scalable_Learned_Index_String_Keys](papers/2020-APSys-SIndex_Scalable_Learned_Index_String_Keys.pdf)
3. [2021-PVLDB-FINEdex-Fine-grained_for_Scalable_Concurrent_Memory_Systems](papers/2021-PVLDB-FINEdex-Fine-grained_for_Scalable_Concurrent_Memory_Systems.pdf)
4. [2022-TOS-Xindex-most-recent](papers/2022-TOS-Xindex-most-recent.pdf)


### Applications

1. [2020-SIGMOD_The_Case_for_a_Learned_Sorting_Algorithm](papers/2020-SIGMOD_The_Case_for_a_Learned_Sorting_Algorithm.pdf)
2. [2022-learned_Similarity Search](papers/2022-learned_Similarity%20Search.pdf)
2. [2022-PVLDB-Endowment-Can_Learned_Models_Replace_Hash_Functions](papers/2022-PVLDB-Endowment-Can_Learned_Models_Replace_Hash_Functions.pdf)
3. [2022-learned_Similarity_Search](papers/2022-learned_Similarity_Search.pdf)
2. [2023-ASPLOS-LeaFTL-Learning-Based Flash Translation Layer for Solid-State Drives](papers/2023-ASPLOS-LeaFTL-leared_FTL_for_SSD.pdf) Learned index for SSD FTL page-level memory mapping

### Linear Model help traditional index (e.g., hybrid Btree + learned index)
[2019-Workshop on Applied AI for Database Systems and Applications Accelerating B+tree search by using simple machine learning techniques]
[2019-Proc. of the Int.Conf. on Extending Database Technology Interpolation-friendly B-trees: Bridging the gap between algorithmic and learned indexes]
[2019-Int. Conf. on Web Information Systems and Applications. Hybrid indexes by exploring traditional B-Tree and linear regression.]
