# Functional-Decomposition
Uses multithreading and parallelism to simulate wild life in a fictional park.

Assisted with the help of Mike Bailey.

Here the simulation simulates the following in a park:
**Temperature** - Under the watcher.
**Precipitation** - Under the watcher.
**Grain Height**
**Deer Population**
**Wario (tourist population)**

These are simulated with a series of sections that are divided based on barriers, where each thread represents each agent, where one does its calculations and waits for the others to complete their calculations for each month.

```
  omp_set_num_threads( 4 );	// or 4
  InitBarrier( 4 );		// or 4
  #pragma omp parallel sections
  {
	  #pragma omp section
	  {
		  Deer( );
	  }

	  #pragma omp section
	  {
		  Grain( );
	  }

	  #pragma omp section
	  {
	    Watcher( );

	  }

	  #pragma omp section
	  {
		  Wario( );
	  }
  }
```

Dividing each task into different sections allows for faster computation using different threads and cores of a processor.

## Results
The graph and table results of running the program can be viewable in the [Report PDF File](https://github.com/andrew-sabin/Functional-Decomposition/blob/main/Proj02.pdf).
