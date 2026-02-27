Simulation Models :: neocortex
------------------------------

These hoc and mod files implement the neocortex specific cell mechanism.


Versions
--------

2019.1 - First import after splitting of neurodamus and models
2021.11 - Start using aggregate neurodamus-models repo, drop common submodule


Common models
-------------

Most Blue Brain models depend on a set of common mods, among them ProbAMPANMDA and ProbGABAAB.
Previously the current repo would include them as a submodule. However, besides overly
complicating the deployment process, it could lead to situations of outdated versions of these files.

Since 2021.11 all BBP maintained models therefore drop submodules and instead use symbolic links to reference the latest versions of the common files.
