Software Installation via Spack at ALCF:  Policy and best practices 

 

Definitions: 

System spack – the spack installation at ~spack/spack-dev, owned by service user ‘spack’, including all software installed via spack, and maintained by operations. 

User spack – spack installation of a user, by a user, for a user, in the user’s own filespace.  

 

Software installation to the system spack area via spack is allowed exclusively by users in the ‘software’ group. This allows for tracking of which user installed a particular build of a particular package, and thus a first-line contact for the software. Software installed to the system spack area is expected to be built and installed correctly (built for the right architecture, with reasonable optimizations, includes, libraries, etc. Installed to a standard place). Experimental and development packages should not be placed here unless they are specifically being deployed for testing or broader consumption, and reasonable effort should be made to communicate the experiemental nature and state of the software, e.g. by including a message in the software’s module when loaded. Software installation to an individual user’s area is allowed by either of three mechanisms:  

Direct use of the system spack via per-user settings in ~/.spack (currently prohibited because of a bug in spack)  

Upstream leverage of the system spack from a user spack. 

Standalone self-installed user spack instance.  

Dangerous or malicious software found in system spack will be removed immediately and reported to software committee.  

 

Page Break
 

Requests for software installation should be routed through support@alcf.anl.gov. Most requests for software installation should be addressable via these policy guidelines, outside of the software committee. Appeals to decisions and clarifications of policy will be addressed by the software committee.  

Things to consider when installing a particular piece of software: 

Will anyone else benefit from using my installation? 

What will the burden of maintaining the installation?  

Would this be best installed via spack or via another mechanism? 

Should this be installed to a shared area or to the user’s home or project space?  

Not every piece of software can be installed via spack, and some codes that can, are still best installed via another mechanism. E.g. a code such as singularity which runs with suid capabilities may have a spack recipe, but since it requires root to install, and since there are potential vulnerabilities for it being installed on a shared filesystem, it goes directly into the iso image.  

 

Software Czar 

 

References: 

 

 

Current Layout and Proposed Layout: 

*?/soft/accttools - owned by harms/software, last written Feb 6, 2019 

/soft/applications - various owners, mostly MD applications, frequent updates 

/soft/buildtools - cmake, elfutils, and trackdeps, regular updates 

/soft/cobalt - owned by prich/catalyst, last written Dec 2018 

/soft/compilers - go, intel, llvm; verious owners 

/soft/condor - owned by acherry/software, last written Mar 2017 

/soft/data-transfer – owned by acherry, software; globus-6.0 

/soft/datascience - many packages, many owners, mostly software group 

/soft/debuggers - owned by rloy, various groups  

*?/soft/environment - owned by rloy, mostly modules, plus bin/whatami, empty lmod dir 

*/soft/gbtest - owned by gabrown, empty 

/soft/interpreters - owned by wscullin; python and julia versions, not the intel ones 

/soft/libraries - various. Includes boost, bolt, memkind-static, etc 

/soft/licensing - owned by acherry 

/soft/packaging - william’s spack installation 

/soft/perftools - owned by rloy, contains darshan, hpctoolkit, tau, etc. 

/soft/spack - owned by spack/software; home directory for spack service user 

*?/soft/tools - owned by harms, texlive is only entry 

*/soft/versioning owned by tjackson, contains subversion only 

/soft/visualization - visualization apps, owned by root/software  

 

*Starred items to be removed or *? folded into other area 

Ask people what things are.  

What needs to be added? Stuff retired from the ISO? E.g. /soft/iso/path/to/thing/in/iso, e.g.  

 

Module file locations: 

 

 

 
