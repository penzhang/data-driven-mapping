	In this folder, you can find the source codes and
input data-dependence matricies.

To run the Strassen algorithm, you need:

[1] You need to install Boost and Boost.Process and ThreadPool.
	[1.a] Boost 1.55.0.
	[1.b] Boost.Process (http://www.highscore.de/boost/process/)
	[1.c] ThreadPool 0.2.5 (http://threadpool.sourceforge.net/index.html)

[2] You can find the source codes for Strassen in ./strassen.
	The main funcion is in ./strassen/strassen_main.cpp.
	The data-dependency matrix files are:
	[2.a] Strassen method  : ./strassen-dmp/mat_strassen.dep
	[2.b] Native MM method : ./strassen-dmp/mat_multi.dep

[3] You can use MSVC (Microsoft Visual Studio 2010) to run it.
	Command Arguments: 5000 mat_strassen.dep 10
	It means matrix size = 5000, using 10 processes, and
	using the data-dependence matrix in mat_strassen.dep.
	
	
To run the Cholesky inversion algorithm, you need:

[1] Do the same procedure as mention in above [1].

[2] You need the source codes in ./strassen and ./cholesky.
	The main funcion is in ./cholesky/cholesky_main.cpp.
	The data-dependency matrix file is:
	./cholesky-dmp/mat_cholesky.dep
	
[3] You need to generate a SPD matrix as input for Cholesky.
	Here is a program that can help create a SPD matrix.
	You can find the code: ./cholesky-dmp/generateSPDmatrix.m
	Usage:
	[3.a] A = generateSPDmatrix(5000); % create the matrix
	[3.b] dlmwrite ('input_5000.txt', A, ' '); % save the matrix
	Then, make sure you have the file - input_5000.txt in your
	working directory.	
	
[4] You can use MSVC to run the program.
	Command Arguments: 5000 mat_cholesky.dep 7
	It means matrix size = 5000, using 7 processes, and
	using the data-dependence matrix in mat_cholesky.dep.
	
	6/5/2014
	
Publications:

[1] Zhang, P., Ling, L., Deng, Y., "A Data-driven Paradigm for Mapping Problems", Parallel Computing, vol. 48, pp. 108-124, 2015. DOI: 10.1016/j.parco.2015.05.002
[2] Zhang, P., Gao, Y., "Matrix Multiplication on High-Density Multi-GPU Architectures: Theoretical and Experimental Investigations", in Lecture Notes in Computer Science, vol. 9137, pp 17-30, 20 June 2015. DOI: 10.1007/978-3-319-20119-1_2
[3] Zhang, P., Gao, Y., Qiu, M., "A Data-oriented Method for Scheduling Dependent Tasks on High-density Multi-GPU Systems", in High Performance Computing and Communications (HPCC), 2015 IEEE 17th International Conference on, New York, NY, August 24-26, 2015, pp. 694-699. DOI: 10.1109/HPCC-CSS-ICESS.2015.314

By Dr. Peng Zhang
URL: https://www.researchgate.net/profile/Peng_Zhang79

3/31/2016
