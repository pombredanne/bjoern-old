python-bjoern
==

Introduction
--

A thin python interface for the binary analysis version of joern
(bjoern) and a set of useful utility traversals.

Dependencies:
--

+ py2neo 1.6.1 (http://book.py2neo.org/en/latest/)
+ py2neo-gremlin (https://github.com/fabsx00/py2neo-gremlin/)

### Installation

	$ sudo pip2 install git+git://github.com/fabsx00/python-joern.git

### Example

The following is a simple sample script. It connects to the database
and runs a gremlin traversal to retrieve all node with attribute
'code' set to '_init'.

```lang-none

from bjoern.all import BjoernSteps

j = BjoernSteps()

j.setGraphDbURL('http://localhost:7474/db/data/')

# j.addStepsDir('Use this to inject custom steps')

j.connectToDatabase()

res =  j.runGremlinQuery('g.idx("nodeIndex")[[code:"_init"]]')

for r in res:
    print r
```
