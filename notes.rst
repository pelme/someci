========
08-17-15 
========


.. contents:: Table of Contents


********************************************
What are our expectations on a build server?
********************************************

Ronny
=====

- code checks, linters, deployment step
- run the complete build pipeline locally
- superset of tox
- multiple nodes in a single pipeline
- each step in the pipeline should be runnable on each node
- possible to do multiple steps in the same part of the pipeline
- set up dependencies so time consuming jobs are not always being run

Floris
======
- one node connects to the master, reports
- build matrix
- generic builds
- multi repository support
- one job, multiple repositories
- configuration in version control

Andreas
=======
- having settings/build configuration in travis CI
- configuration in version control (always in sync with your code)

Raphael
=======
- be able to run builds locally while offline
- configuration via textfiles
- configuration for multiple platforms
- collect artifacts of the build steps (docs, pypi distribution, ...)

Maik
====
- best of both worlds travis/jenkins
- UI that presents results
- clear definition of how a job is structured (maybe changeable using plugins), maybe use Bamboo's definition: a job contains stages (run in parallel) and stages contain tasks (run sequentially)
- batteries included for python best practises
- dynamic branches (plan branches in bamboo)
- platform independent configurations


*********************************
Additional thoughts and questions
*********************************

Ronny
=====
- send test results back to the build server (idea from devpi?)
- keep it as simple as possible and stick to pure python (to be platform agnostic)

Ronny's CI project
------------------
- uses couchdb to sync state changes to worker nodes. puts job description into a document and lets couchdb sync docs to nodes

Projects to look at
===================
- python-effect
- pluggy
- https://reg.readthedocs.org/en/latest/

