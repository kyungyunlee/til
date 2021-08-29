# Database storage

Database is stored on disk, so the DBMS has to bring the data into memory.

In DBMS, the query execution engine will ask the buffer pool to return specific data. The buffer pool is responsible for moving the data into and out of memory.

<img src="https://i.loli.net/2021/08/23/zWqauc4I5HXNPBV.png" alt="스크린샷 2021-08-23 오후 9.50.05" style="zoom:67%;" />

DBMS essentially is similar to the concept of virtual memory, in that the user is tricked to believing that their entire database is available in memory, but in reality, only a small amount of data is cached locally. 
Instead of relying on OS, DBMS implements its own disk to memory operations.


### Files and pages 
Data is organized as files in the disk, which are composed of one or more pages. Commonly, page size varies from 512MB to 16KB. 
Pages are fixed-sized atomic unit of data. 

### How are files stored?  
It is responsible for managing files. It organizes files as a collection of pages. 

### How are pages stored? - Heap file organization
We need to track which pages are where and which ones are empty.
It is often implemented as page directory structure, where there is a special page, called "page directory", which tracks all the pages in the database.




<img src="https://i.loli.net/2021/08/23/2wGyhsFfat73NOT.png" alt="스크린샷 2021-08-23 오후 9.55.38" style="zoom:50%;" />



### Within the page, how are data organized? - Slotted pages 
Within each page, variable sized tuples are stored along with its slot id. The header contains the metadata about the tuples in the page, and from the beginning of the page, each slot's offset is saved.

The actual tuple data is stored from the end of the page. 

<img src="https://i.loli.net/2021/08/23/UH9xefQkmWjcC3r.png" alt="스크린샷 2021-08-23 오후 9.58.26" style="zoom:50%;" />



### Reference

* All images and notes from CMU database course 

  
