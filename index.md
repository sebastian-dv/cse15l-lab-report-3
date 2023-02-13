# Command Research: grep
**The commands were all found [here](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)**
---
1. -i  
The -i option ignores cases so it looks for any matching words regardless of the case.
---
`$ grep -i CARNIVAL WhatToHongKong.txt
        the carnival atmosphere of the Cheung Chau Bun Festival, with its high`
`$ grep -i aloha WhatToHawaii.txt
        landing) who nest there. Aloha Airlines offers scheduled flights to`
        
Both commands contain a word, all uppercase for the first and lowercase for the second, but the output shows that the word contained in the text is not in the same case as the word I searched for. This shows how the -i option could help looking for any mention of a word, regardless of the case it's in within the text you are searching through.
