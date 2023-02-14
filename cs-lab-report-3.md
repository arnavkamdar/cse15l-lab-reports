# Lab Report 3: Usage of the command 'Grep'

For this lab report, I researched the linux command 'grep', coming across various intricacies and interesting command options in its usage. I have summarized four of these commands, which shall be highlighted below. 

## Command 1: **`grep -r`**
`grep -r` is a tool that recursively searches through repositories. Most `grep` commands must be executed on a specific file to search the file, but this allows a user to specifically search directories and every file within them. `-r` is therefore a very powerful tool, as it enables a user to search every file within a requested repository. One instance where this is useful is if a teacher wants to find a student's information via their name in a repository where each student's information is saved on a different text file. 

The usage of this command is `grep -r "search string" directory/file_path`

The source where I learnt about this command was [this website](https://www.computerhope.com/unix/ugrep.htm) that explains many grep commands with detailed examples.

Following are some examples of `grep -r`'s usage. 

### Example 1: Using `grep -r` to find the word "Lucayans" within a repository of text files.[^1]
[^1]: This example is derived from my solution to the [skill demonstration](https://edstem.org/us/courses/31260/discussion/2510885).


<code><i>Input:</i></code>
<br>
<code>$ grep -r "Lucayans" written_2</code>


<div style="text-align: justify">
<code><i>Output:</i></code>
<br>
<code>written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the <mark>Lucayans</mark>. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.</code>
</div>
<div style="text-align: justify"> 
<code>written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the <mark>Lucayans</mark> within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
</code>
</div>

The instances of Lucayans, on git bash, are colored red so that the user may locate them. As evidenced here, the command has browsed through every file in written_2 and outputted the two results of "Lucayans" that it has found, both in the same file, `Bahamas-History.txt`. 

### Example 2: Using `grep -r` to find the word "freely" within a single text file. 

<code><i>Input:</i></code>
<br>
<code>$ grep -r "freely" written_2/non-fiction/OUP/Fletcher/ch10.txt</code>

<div style="text-align: justify"> 
<code><i>Output:</i></code>
<br>
<code>Under modern capitalism there are many conditions that render choices less than fully free. Material necessity is the most obvious. But, as we have learned from the history of alcohol and cigarette consumption, advertising and peer group influence can lead people to develop habits that they later regret. The same is true of heroin consumption, which may readily develop into a condition of dependency in which the addict may enjoy the illusion of <mark>freely</mark> choosing not a hole bored in his ear but rather numerous telltale holes bored in his veins.</code>
</div>

As seen above, the word "freely" has been found even when a file is given in the input command. `grep -r` therefore allows a user to thoroughly search for a string, be it in a file or repository. 

## Command 2: **`grep -n`**
`grep -n` is a tool that allows a user to see the line number at which a string is found within a file. It can only be used on a file (not a directory), unless `grep -r` is used in concatenation with it. The line number is printed at the beginning of each output result. 

The usage of this command is `grep -n "search string" file-path/file-name`

The source where I learnt about this command was the [same website](https://www.computerhope.com/unix/ugrep.htm) as before. 

### Example 1: Using `grep -n` to find the instances of the word "outside" within a single text file. 

<code><i>Input:</i></code>
<br>
<code>$ grep -n "outside" written_2/travel-guide written_2/travel_guides/berlitz2/Paris-WhatToDo.txt</code>

<div style="text-align: justify"> 
<code><i>Output:</i></code>
<br>
<code><mark>40:</mark>Small children are bound to enjoy the merry-go-round, puppet theaters (<mark>outside</mark> July and August), and pony rides in the Jardin du Luxembourg. They can also watch the toy boats capsize in the fountain. For the scientifically minded, there’s a great deal to learn painlessly in the Cité des Sciences et de l’Industrie at La Villette (see page 72). The Palais de la Découverte (see page 75) makes use of a similar hands-on approach.</code>
</div>
<div style="text-align: justify"> 
<code><mark>41:</mark>Some 30 km (20 miles) <mark>outside</mark> Paris at Marne-la-Vallée, the Disneyland Paris Resort could keep kids happy for several days (see page 80). Fans of the Astérix comics about ancient Gaul and the Romans will enjoy the Parc Astérix theme park, near Autoroute A1 between Roissy (Charles-de-Gaulle airport) and Senlis, open April to October; Tel. 03 44 62 34 34. France Miniature is a 5-hectare (7.5-acre) relief map of France including model villages, châteaux, and monuments to a scale of 1:30 (RER train to St-Quentin-en-Yvelines, then bus; open daily, 15 March–15 November).</code>
</div>

As seen above, numbers appear before each output block, indicating what line of the file the word was found at. This allows for ease of perusal of documents, and can be used to browse and navigate through large text files without having to manually search for the word. 

### Example 2: Using `grep -n` along with `grep -r` to find instances of the word "underbelly" in a repository.

<code><i>Input:</i></code>
<br>
<code>$ grep -n -r "underbelly" written_2</code>

<div style="text-align: justify">
<code><i>Output:</i></code>
<br> 
<code>written_2/travel_guides/berlitz1/WhatToIndia.txt:<mark>213</mark>:        the <mark>underbelly</mark> of the wild Himalayan goats. Then, just when you think</code>
</div>
<div style="text-align: justify"> 
<code>written_2/travel_guides/berlitz2/PuertoRico-History.txt:<mark>24</mark>:The Spanish-American War was no great challenge for the US force that landed at Guánica, on Puerto Rico’s calm south coast, rather than at fortified San Juan. Military resistance was spotty at best. By starting at the soft <mark>underbelly</mark>, the 16,000 troops of General Nelson A. Miles gained control of the island in less than three weeks. The central issue that had drawn Spain and the United States into war — Cuba’s struggle for independence — was resolved in that island’s favor: Cuba’s freedom was guaranteed by the Paris Treaty of 1898. But Spain’s two other major colonies, the Philippines and Puerto Rico, simply changed hands, becoming colonies of the United States.</code>
</div>

As seen above, two commands can be used together to achieve a required output. Using `-r` and `-n` together shows the files where the instances were found, as well as the line numbers in each file where these strings were located. 

## Command 3: **`grep -i`**
`grep -i` is a command that makes a search case-insensitive; that is, it finds all instances of a string regardless of whether letters are uppercase or lowercase in it.  It can only be used on a file (not a directory), unless `grep -r` is used in concatenation with it. This is very useful, as some words may appear at the beginning of sentences and be excluded from a normal `grep` search, as the first letter would be in uppercase. 

The usage of this command is `grep -i "SeArCh StRiNg" file-path/file-name`, and will search for "search string", "SEARCH STRING", and every possible combination of uppercase and lowercase letters in between. 

I learnt about this command from the [same source](https://www.computerhope.com/unix/ugrep.htm) as I did the other commands.

### Example 1: Using `grep -n` to find the instances of the word "outside" within a single text file. 

<code><i>Input:</i></code>
<br>
<code>$ grep -i "MoDeRn" written_2/travel_guides/berlitz2/Paris-WhatToDo.txt</code>

<div style="text-align: justify">
<code><i>Output:</i></code>
<br> 
<code>The large <mark>modern</mark> shopping malls include the Forum des Halles, Centre Maine-Montparnasse, and the Palais des Congrès at Porte Maillot.
<mark>Modern</mark> dance is enjoying a revival, with a new wave of small, imaginative companies beginning modestly enough at the Café de la Danse (passage Louis-Philippe) and Théâtre Garnier before reaching the heights of the Théâtre de la Bastille.</code>
</div>
<div style="text-align: justify"> 
<code>Floor shows keep the “naughty” image of Paris alive. The Folies Bergères (rue Richer), which launched the careers of Josephine Baker, Mistinguett, and Maurice Chevalier, and the Lido on the Champs-Elysées are both classic survivors. The most famous <mark>modern</mark>-day floor show, erotic, brilliantly choreographed, and bordering on chic, is at the Crazy Horse Saloon (avenue George V). Toulouse-Lautrec painted the showgirls of the Moulin Rouge (place Blanche) a century ago, and it still offers tourists a boisterous floor show in the old tradition. The rest of Pigalle plumbs the lower depths with a certain fascinating glee.</code>
</div>

The instances of modern have been highlighted by me for ease of viewing, but the command's utility is evident: "modern" and "Modern" were both located by this command, something that would not have occured without `-i`.

### Example 2: Using `grep -i` along with `grep -n` and `grep -r` to find case-insensitive instances of the word "Whale-watching" in a repository.

<code><i>Input:</i></code>
<br>
<code>$ grep -i -r -n "Whale-watching" written_2</code>

<div style="text-align: justify">
<code><i>Output:</i></code>
<br>
<code>written_2/travel_guides/berlitz1/WhatToLosAngeles.txt:212:        try a gondola cruise at Long Beach. <mark>Whale-watching</mark> expeditions are also</code>
</div>
<div style="text-align: justify"> 
<code>written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:858:        of the region. It’s also a prime spot for <mark>whale-watching</mark> during the
  
...
</code>
</div>

As seen above, there is no limit on the number of commands that can be used together to achieve a required output. Using `-i`, `-r`, and `-n` together shows the files where the case-insensitive instances were found, as well as the line numbers in each file where these strings were located. There were many more instances, but for the sake of brevity, I used ellipses to exclude them in this code block.

## Command 4: **`grep "string1.*string2"`**
`grep "string1.*string2"` is an extremely useful command that allows a user to obtain entire sentences, blocks of words, or paragraphs, without needing to specify every word in the desired output. The `"."` character in Linux is a single-character wildcard, and `"*"` takes a special meaning here: all preceding-characters match the desired string. Effectively, the two characters used together create a command that returns **all characters between string1 and the last instance of string2  in a line (inclusive of string1 and string2)**. This is extraordinarily useful as it effectively removes the user's need to actually access the file to utilize the strings: the sentence can simply be copied through the output. Additionally, it helps you find multiple similar strings; for example, "that boy" and "that specific boy" would both be found by `grep "that.*boy"` but only the former would be found through the search `grep "that boy"`. 

The usage of this command is `grep "string1.*string2" file-path/file-name`, and will search for every instance of characters between string1 and string2. 

As above, I learnt about this command from the [same source](https://www.computerhope.com/unix/ugrep.htm).

### Example 1: Using `grep "string1.*string2` to find sentences containing "As for" in the file Bahamas-History.txt. 

<code><i>Input:</i></code>
<br>
<code>$ grep "As for.*." written_2/travel_guides/berlitz2/Bahamas-History.txt</code>

<div style="text-align: justify">
<code><i>Output:</i></code>
<br>
<code>The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. <mark>As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.</mark></code>
</div>

As evidenced by the code, the command found the string "As for" and returned all characters between "As for" and ".". 

### Example 2: Using `grep "string1.*string2` to find sentences containing "Lucayans" in the file Bahamas-History.txt.
<code><i>Input:</i></code>
<br>
<code>$ grep "Lucayans.*." written_2/travel_guides/berlitz2/Bahamas-History.txt</code>

<div style="text-align: justify">
<code><i>Output:</i></code>
<br> 
<code>Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the <mark>Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.</mark></code>
</div>
<div style="text-align: justify">
<code>The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the <mark>Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.</mark></code>
</div>

Running the code above led me to realize a small setback of using this command. In the first result, there is a period right after the word Lucayans, but the search ends at the period of the next sentence. While I initially thought that the search would end at the first instance of string2, I realized here that it ends at the last instance of string2 in the given line. Thus, if more than one sentence is present in one line, the utility of this function could be reduced. 

This highlights the importance of hands-on testing, as I would not have made this discovery by simply reading the website's description of the command. 


---

These are a few interesting commands I came across when researching how to use the command `grep`!
