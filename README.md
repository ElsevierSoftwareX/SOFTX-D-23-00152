# netDFT : JAVA Density Functional Theory For Solid 
netDFT is a Java program to solve the KSDFT equation using the pseudopotential method to get a solid's band structure and total energy.
## Features
- SCF with electron density mixing
- Band structure calculations
- LDA-PZ functionals
## Requirements
- Linux OS
- Java (https://www.java.com/en/download/) version >= 11

## Installation
You can download the package zip file (using Github) or clone this repository to your computer. You can freely extract it into the folder you like.

## Input File Descriptions
-   smar[1,0] : Gaussian smearing for metals (set 1 for smearing)

-   random [1,0] : Initial wave function initiation using random number (set 0 for random )

-   usp [1,0] : The pseudopotential used is the type of ultrasoft
    psudopotential (set 1 for ultrasoft psudopotential)

-   celldm : Crystallographic constants

-   ecutwfc : Kinetic energy cutoff (Ry) for wavefunctions

-   ecutrho : Kinetic energy cutoff (Ry) for charge density and
    potential For norm-conserving pseudopotential

-   ibrav : Bravais-lattice index

-   iband : Number of electronic states (bands) to be calculated.

-   num\_atom : Number of types of atoms in the unit cell

-   nat : Number of atoms in the unit cell

-   mix : Mixing factor for self-consistency

-   pos : Atomic positions are in cartesian coordinates, in units of the
    lattice parameter (either celldm(1) or A).

-   k\_point : Read k-points in cartesian coordinates.
## Example calculations

Total energy
------------

    {
        "status": "scf",
        "smar": 0,
        "random": 0,
        "usp": 0.0,
        "celldm": [10.2, 0.0, 0.0, 0.0],
        "ecutwfc": 18.0,
        "ecutrho": 72.0,
        "ibrav": 0,
        "iband": 6,
        "num_atom": 1,
        "nat": 3,
        "mix": 0.7,
        "atom": ["Si"],
        "upf_url": ["/home/agung/Documents/kkk/q-e-qe-6.6/pseudo/Si.pz-vbc.UPF"],
        "lattice": [
            [10.2, 0.0, 0.0],
            [0.0, 10.2, 0.0],
            [0.0, 0.0, 10.2]
        ],
        "degauss_": 0.02,
        "pos": [
            [0.0, 0.0, 0.0],
            [0.25, 0.25, 0.25],
            [0.3, 0.3, 0.3]
        ],
        "atom_pos": [0, 0, 0],
        "weig": [2.0],
        "k_point": [
            [0.0, 0.0, 0.0]
        ]
    }

For this example, the psudo files can be found in the psudo folder.
To run netDFT total energy calculation, execute this command on terminal. You have to run this command inside the netDFT folder. The results of the calculations will be stored in the out.dat file.

    java -jar "url_netDFT_folder/dist/netDFT.jar" url_input_file/input.dat > out.dat
     

Band Structure
--------------

You must first perform a total energy calculation to perform a structural band calculation.

    {
        "status": "nscf",
        "smar": 0,
        "random": 0,
        "usp": 0.0,
        "celldm": [10.2, 0.0, 0.0, 0.0],
        "ecutwfc": 18.0,
        "ecutrho": 72.0,
        "ibrav": 0,
        "iband": 6,
        "num_atom": 1,
        "nat": 3,
        "mix": 0.7,
        "atom": ["Si"],
        "upf_url": ["/home/agung/Documents/kkk/q-e-qe-6.6/pseudo/Si.pz-vbc.UPF"],
        "lattice": [
            [10.2, 0.0, 0.0],
            [0.0, 10.2, 0.0],
            [0.0, 0.0, 10.2]
        ],
        "degauss_": 0.02,
        "pos": [
            [0.0, 0.0, 0.0],
            [0.25, 0.25, 0.25],
            [0.3, 0.3, 0.3]
        ],
        "atom_pos": [0, 0, 0],
        "weig": [0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407, 0.07407407407407407],
        "k_point": [
            [-1.0, 0.5, 0.0],
            [-0.9667, 0.4833, 0.0],
            [-0.9333, 0.4667, 0.0],
            [-0.9, 0.45, 0.0],
            [-0.8667, 0.4333, 0.0],
            [-0.8333, 0.4167, 0.0],
            [-0.8, 0.4, 0.0],
            [-0.7667, 0.3833, 0.0],
            [-0.7333, 0.3667, 0.0],
            [-0.7, 0.35, 0.0],
            [-0.6667, 0.3333, 0.0],
            [-0.6333, 0.3167, 0.0],
            [-0.6, 0.3, 0.0],
            [-0.5667, 0.2833, 0.0],
            [-0.5333, 0.2667, 0.0],
            [-0.5, 0.25, 0.0],
            [-0.4667, 0.2333, 0.0],
            [-0.4333, 0.2167, 0.0],
            [-0.4, 0.2, 0.0],
            [-0.3667, 0.1833, 0.0],
            [-0.3333, 0.1667, 0.0],
            [-0.3, 0.15, 0.0],
            [-0.2667, 0.1333, 0.0],
            [-0.2333, 0.1167, 0.0],
            [-0.2, 0.1, 0.0],
            [-0.1667, 0.0833, 0.0],
            [-0.1333, 0.0667, 0.0]
        ]
    }

To run netDFT band structure calculation, execute this command on terminal. You have to run this command inside the netDFT folder.

    java -jar "url_netDFT_folder/dist/netDFT.jar" url_input_file/input.dat > out.dat
     
## Example of Cu's band structure calculations

<img src="https://github.com/AgungDanuWijaya/netDFT/blob/main/cu_fix.png" alt="dftk logo" height="400px" />
The input file for this example can be accessed in the example folder.

## Cluster band structure calculations

<img src="https://github.com/AgungDanuWijaya/netDFT/blob/main/netdft.drawio.png" alt="dftk logo" height="400px" />

- Client configuration
  - ssh-keyscan -H -t rsa ip_job_control >> /url_folder/job_control
  - ssh-keyscan -H -t rsa ip_worker_1 >> /url_folder/worker_1

- Job control configuration
  - install mysql server (https://dev.mysql.com/downloads/mysql/)
  - run script WORK.SQL on mysql server . You can get script from https://github.com/AgungDanuWijaya/netDFT/blob/main/Dump20230304.sql
  - copy netDFT on  /root/

- Worker Configuration
  - ssh-keyscan -H -t rsa ip_job_control >> /root/.shh/known_ssh
  - copy netDFT on  /root/

- Running netDFT on cluster
  - Copy psudo file on directory /root/kuda on server job control
  - Open netDFT on netbeans (https://netbeans.apache.org/)
  - running input_cluster.java in package cluster
  - running run_cluster.java in package cluster
------------
        
	{
	"cs": {
		"host": "your_ip_database and ssh serve",
		"user": "your ssh user",
		"user_db": "your_mysql_user",
		"pass": "your_database_and_ssh pass, please make same database and ssh password in all computer",
		"key": "/root/.ssh/known_hosts"
	},

	"degauss_": 0.02,
	"status": "bands",
	"smar": 1,
	"random": 0,
	"usp": 1.0,
	"celldm": [6.73, 0.0, 0.0, 0.0],
	"ecutwfc": 25.0,
	"ecutrho": 300.0,
	"ibrav": 2,
	"iband": 16,
	"num_atom": 1,
	"nat": 1,
	"mix": 0.7,
	"atom": ["Cu"],
	"upf_url": ["/root/kuda/Cup.upf"],
	"usp_": [1],
	"pos": [
		[0.0, 0.0, 0.0]
	],
	"atom_pos": [0],
	"weig": [2.0],
	"k_point": []
    }
    
Above is exampe of input configuration file for get band structure of Cu. The location input file must be setting on input_cluster.java, in localDir.

------------

    String Server[] = {"ip_job_control", "ip_worker_1", "ip_worker_1", "ip_worker_1", "ip_worker_1"};
    String key[] = {"/url_folder/job_control", "/url_folder/worker_1", "/url_folder/worker_2", "/url_folder/worker_3", "/url_folder/worker_4"};

Please edit the server and host key on input_cluster.java and run_cluster.java, based on the Server and key array (above script) and the host key obtained in the previous step on the client configuration.  
## ScaLAPACk
We've added ScaLAPACK to be an alternative to LAPACK. In the JNIJava_.java code file, You can choose to use gev_object a=new JNIJava().main(H, S, iband) for LAPACK, and gev_object a = new scalapackJava().main(H, S, iband) for ScaLAPACK.
     
