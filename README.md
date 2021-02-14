# DoFS_using_ML
Detection of False Sharing Using Machine Learning 

## Abstract
False sharing is a major class of performance bugs in parallel
applications. Detecting false sharing is difficult as it does not
change the program semantics. We introduce an efficient and
effective approach for detecting false sharing based on machine
learning. 

## Mini Programs for learning
<pre>
<code>
int psum[MAXTHREADS]; // shared by threads
int v1[N], v2[N];
void *pdot_1(...) // Method 1: Good
{ ...
 int mysum = 0;
 for (i = start; i < end; i++)
 mysum += v1[i] * v2[i];
 psum[myid] = mysum;
}
void *pdot_2(...) // Method 2: Bad -
{ ... // False sharing
 for (i = start; i < end; i++)
psum[myid] += v1[i] * v2[i];
}
void *pdot_3(...) // Method 3: Bad
{ ... // Memory access
 // same as pdot_1() except non-sequential
 // vector element access (e.g, strided)
}
</code>
</pre>
