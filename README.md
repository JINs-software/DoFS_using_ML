# DoFS_using_ML
Detection of False Sharing Using Machine Learning 

## Abstract
False sharing is a major class of performance bugs in parallel
applications. Detecting false sharing is difficult as it does not
change the program semantics. We introduce an efficient and
effective approach for detecting false sharing based on machine
learning. 

## Mini-programs for Training 
example: Code for parallel computation of dot-product 
<pre>
<code>
int psum[MAXTHREADS]; // shared by threads
int v1[N], v2[N];

// Method 1: Good
void *pdot_1(...) 
{ ...
 int mysum = 0;
 for (i = start; i < end; i++)
 mysum += v1[i] * v2[i];
 psum[myid] = mysum;
}
// Method 2: Bad False sharing
void *pdot_2(...) 
{ ... 
 for (i = start; i < end; i++)
psum[myid] += v1[i] * v2[i];
}
// Method 3: Bad Memory access
void *pdot_3(...) 
{ ... 
 // same as pdot_1() except non-sequential
 // vector element access (e.g, strided)
}
</code>
</pre>

## Identification of Performance Events
Using perf version 5.10.9

## TRAINING A MACHINE CLASSIFIER
<pre>
<code>
// 의사결정트리
clf = tree.DecisionTreeClassifier()
clf = clf.fit(data, target)

// KNN
clf = neighbors.KNeighborsClassifier(5)
clf.fit(X,y)
</code>
</pre>

