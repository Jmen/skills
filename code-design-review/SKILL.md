---
name: code-design-review
description: 
---

1. Can you understand the change just from the definition of the tests?

- list out the tests
- do they cover all of the requirements?
- imaging the simplest implementation from the definition of the test
- does the actual solution code match up with this?

2. If this code failed in Production, would we know about it?

- is there enough context around the request parameters in the logs to debug the issue?

3. Are there any performance issues?

- ask for information about the volume of traffic passing through the affected code paths
- don't optimise prematurely, balance against readability of the code

4. Produce a Security Threat Model using STRIDE

5. Provide an order to read the actual files, to understand the change in the easiest way

e.g. test file, handler, then database access

- group by vertical functions, if the code structure supports it

e.g. create resource, read resource, update resource