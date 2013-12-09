Malloc
------



Developers
==============
* Megan Murray
* Mush Kapadia


Implementation
==============
Our imlementation uses a doubly linked list, which consists of nodes with a next, pref pointer along with the size of the contents and a flag free to determine if this space is free. As space is malloc'd the linked list contains nodes for all of the memory that is malloc'd and if it is currently free or not (able to be overwritten).  So when free is called, we search through the list and mark the node/block as free.  Free also checks if the previous or next nodes are free, so we can then merge these blocks together to keep larger chunks of memory and avoid fragmentation. I took the tradeoff of storing the pref pointer in the header to avoid searching through the linked list each time a free is called for the merge.

###Effciency 
