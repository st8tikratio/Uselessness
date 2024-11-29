---
title: Random Logic
tags: [principles, ' governance', ' cardano', ' constitution']

---

---
tags: principles, governance, cardano, constitution
---

# Random Logic

### Distribution #1

In this distribution, since the wallets were collected via participant entry into a document, the only randomness required was to determine which four (4) NFTs would go to each participant. Final numbers are in [Distribution No.1](/91GaRJMVR9KdJk9GZzoVkg).

```
import random

list = ['Decentralization', 'Educational', 'Equality', 'Honesty', 'Inclusivity', 'Self-Sovereignty', 'Sustainability', 'Transparency']
# list = [1, 2, 3, 4, 5, 6, 7, 8]   
# or any list of hashes, addresses, etc.
numruns = 0

# adjust [ < n ] as needed
while (numruns < 51): 
    data = [random.sample(list, 4)]
    print ("Random selection is: " + str(data))
    numruns = numruns + 1

print ("Done!" + str(numruns) + " random sets gnerated!" )
```
---

### Distribution #2

None needed. Direct distribution to the project members. See [here](/q3hp87edRmmVhTkULnOQjQ).

---

### Distribution #3

