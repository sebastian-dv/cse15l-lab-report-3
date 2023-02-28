# Command Research: grep
**The commands were all found [here](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)**

---

1. -i  
The -i option ignores cases so it looks for any matching words regardless of the case.
---
```console
$ grep -i CARNIVAL WhatToHongKong.txt
        the carnival atmosphere of the Cheung Chau Bun Festival, with its high
```
```console
$ grep -i aloha WhatToHawaii.txt
        landing) who nest there. Aloha Airlines offers scheduled flights to
```  
Both commands contain a word, all uppercase for the first and lowercase for the second, but the output shows that the word contained in the text is not in the same case as the word I searched for. This shows how the -i option could help looking for any mention of a word, regardless of the case it's in within the text you are searching through.

2. -r  
The -r option searches through files and directories recursively in order to find the target word(s).
---
```console
$ grep -r Lying
        ./travel_guides/berlitz1/WhereToGreek.txt:        Lying closest to Athens and the Attic peninsula, the
        ./travel_guides/berlitz1/WhereToGreek.txt:        Lying a few hundred meters to the west, the island of
        ./travel_guides/berlitz1/WhatToHawaii.txt:        Midway. Lying some 1,100 miles northwest of Honolulu, Midway
        ./travel_guides/berlitz1/WhereToItaly.txt:        Lying at the western end of the Bay of Naples — reached by
        ./travel_guides/berlitz1/WhereToJapan.txt:        Lying the farthest southwest of Japan’s four main islands,
        ./travel_guides/berlitz1/WhereToLosAngeles.txt:        Lying to the north of Huntington Beach is the Bolsa Chica
        ./travel_guides/berlitz2/Costa-WhereToGo.txt:Lying about 50 km (32 miles) east of Granada on the road to Murcia is Guadix, a particularly unusual                       city in that many of its inhabitants are troglodytes. In the Barrio Santiago, there are streets with houses that have their own small front yards and façades that, on the surface, make them indistinguishable from ordinary homes. Look closely, though, and the white, circular chimneys emanating from the rocks give the game away. These are actually caves with a practical use: they’re cool in summer and warm in winter. There is plenty else of interest here, including a Moorish castle dating from the 10th and 11th centuries, a late 16th-century cathedral, and many important palaces, houses, and churches.
        ./travel_guides/berlitz2/Cuba-WhereToGo.txt:Matanzas, 42 km (26 miles) west of Varadero, is busy and grimy. Lying alongside a deep bay, it came into its own during the 19th century as the country’s sugar capital. On the leafy main square, Parque Libertad, the Museo Farmacéutico is a wonderfully preserved chemist’s shop, founded in 1882. On a street running east toward the bay, the Catedral de San Carlos is notable for its many murals, some restored, some badly in need of attention.
```
```console
$ grep -r Oceanarium
        ./travel_guides/berlitz1/WhereToHongKong.txt:        The Oceanarium is said to be the largest in the world, and
        ./travel_guides/berlitz2/CanaryIslands-WhereToGo.txt:Of the coastline south of Puerto del Rosario, the new cosmopolitan development of El Castillo, also known as Caleta de Fuste, is of most interest. Activities here focus around the attractive, horseshoe-shaped beach (where windsurfing is a particularly popular sport), and the well-designed marina. In the marina, there is an area where you can view the fish that frequent its waters, and a small number of activities use the harbor as a homeport. The Oceanarium is a catamaran that will take you out to visit the dolphins and whales, and the Nautilus is a semi-submersible submarine that has twenty individual seats.
```
When typing these commands, I did not have to enter any specific text file to search through, I was still in the written_2 directory. So, this command is helpful when trying to find specific words within a large amount of text files. It saves you the time of searching for the word within each file and just returns the files which contain it and the parts of the texts which have the word.

3. -w  
The -w option has grep only search for the exact word you input, it will not output any words which contain the target word.
---
```console
$ grep -w hour ch1.txt 
        The labor intensive [U.S.] apparel market cannot and should not compete with much lower cost labor elsewhere. The stuff depends on somebody sitting at a sewing machine and stitching sleeves on; it is crazy to hurt American consumers by forcing them to buy that at $4 or $5 an hour of labor. We ought to be out of that business.26
```
```console
grep -w can ch2.txt
        From the nineteenth century on, enterprises in the apparel industry have taken one of three general forms: the manufacturer with an inside shop; the jobber; and the contractor with an outside shop, which can supply either manufacturers or jobbers. The jobber, a form characteristic of women’s apparel, does not produce in a plant that it owns. Jobbers may purchase cloth and materials; design or purchase design of garments; and cut or contract out cutting of fabrics. They turn over sewing and assembly to contractors, and their main role is to merchandise finished product.
```
This command will only show excerpts of a text that contain the exact word that you input. It will not include words that contain the targeted word. For example if the target word was "the", the output would not include words like "these" or "there" which contain the word "the", but aren't the actual word.

4. -l  
The -l option will only return a list of files that contain the target word, this works best with the -r option which will search through a directory recursively in order to find a word.
---
```console
$ grep -lr Lucayans
        ./Bahamas-History.txt
```
```console
$ grep -lr skyscraper
        ./Boston-WhereToGo.txt
        ./California-WhereToGo.txt
        ./Berlin-History.txt
        ./Canada-WhereToGo.txt
        ./Paris-WhereToGo.txt
        ./China-WhereToGo.txt
        ./PuertoRico-WhereToGo.txt
        ./Beijing-History.txt
        ./Poland-History.txt
        ./Beijing-WhereToGo.txt
```
This command is useful when you are trying to find what files contain a certain word, but don't want the terminal to output a large wall of text containing excerpts from the files that contain the word. It is much cleaner to just know which files contain a word and then you could manually enter a desired file and use 'ctrl + f' to look for any instances of that word.

