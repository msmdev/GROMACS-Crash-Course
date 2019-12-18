# GROMACS Crash Course

GROMACS is a very potent and versatile Open Source Molecular Dynamics simulation program.
Since it has no GUI, one has to start, control and run it via the terminal or a shell script.

During the following two days you will
1. learn how to use the Unix/Linux shell (via a terminal),
2. install GROMACS,
3. learn basic GROMACS usage.

During the course it will be assumed that you have Ubuntu 18.04 installed on your Notebook.
Further, you will need internet access.

## 1. The Unix Shell
To install and use GROMACS a basic knowledge regarding the use of the Unix/Linux shell is mandatory.
Thus, you will start with a "Software Carpentry" Unix shell lesson via the following link:

http://swcarpentry.github.io/shell-novice/

## 2. Install GROMACS
You will install GROMACS 2018 (for documentation see: http://manual.gromacs.org/documentation/2018.8/index.html).
Before doing so, you should update our system via

``` sudo apt-get update && sudo apt-get upgrade ```.

Afterwards, at first, you have to download the GROMACS source code from

http://manual.gromacs.org/documentation/2018.8/download.html#source-code

and perform the installation following the instructions on

http://manual.gromacs.org/documentation/2018.8/install-guide/index.html .

You should try the "quick and dirty" installation first, but if you run into trouble in doing so,
you might need to try the more elaborated instructions.

If, during the build process with CMake, while executing

``` bash cmake .. -DGMX_BUILD_OWN_FFTW=ON -DREGRESSIONTEST_DOWNLOAD=ON ```, 

you run into an error like

``` bash
CMake Error at CMakeLists.txt:41 (project):
  No CMAKE_CXX_COMPILER could be found.

  Tell CMake where to find the compiler by setting either the environment
  variable "CXX" or the CMake cache entry CMAKE_CXX_COMPILER to the full path
  to the compiler, or to the compiler name if it is in the PATH.


-- Configuring incomplete, errors occurred!
```

you are missing the C++ compiler.
This can be solved by installing essential compilers and related packages via

``` bash sudo apt-get install build-essential ```

Also, if you want to get the most out of our hardware, i.e., when using a supercomputer,
it will be necessary to perform a optimized installation, 
taking into account specific features of the respective hardware and OS.

## 3. Using GROMACS
Diving into GROMACS for the first time, it is sensible to start with a very basic and well-tried tutorial like

http://www.mdtutorials.com/gmx/lysozyme/index.html

were you will set up a simulation system containing a protein (lysozyme) in a box of water and with ions.

After mastering this, you will go ahead with a more complex and use-case specific tutorial

http://www.mdtutorials.com/gmx/complex/index.html

were you will set up a simulation system containing a protein (T4 lysozyme L99A/M102Q) in complex with a ligand.

In doing so, you have learend the basic concepts and some more advanced aspects of working with GROMACS 
(more precisely: of setting up simulation systems with GROMACS).

## 4. Simulating on a supercomputer
Performing MD simulations on a normal laptop or desktop PC isn't going to be very productive,
since the computing ressources of such a small consumer systems aren't very grand 
and MD simulations of large biomolecular systems are computationally very costly.
Thus, real large-scale production simulations are typically performed on a cluster or supercomputer
enabling the execution of highly parallel calculations on hunreds or thousands of CPUs or even potent GPUs.

To do so, the first thing you need is access to such a supercomputer, 
i.e. the Lichtenberg Supercomputer (HHLR) of the TU Darmstadt.
