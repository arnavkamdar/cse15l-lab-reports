# Lab Report 3: Usage of the command 'Grep'

For this lab report, I researched the linux command 'grep', coming across various intricacies and interesting command options in its usage. I have summarized four of these commands, which shall be highlighted below. 

## Command 1: **`grep -r`**
`grep -r` is a tool that recursively searches through repositories. Most `grep` commands must be executed on a specific file to search the file, but this allows a user to specifically search directories and every file within them. `-r` is therefore a very powerful tool, as it enables a user to search every file within a requested repository. One instance where this is useful is if a teacher wants to find a student's information via their name in a repository where each student's information is saved on a different text file. 

The usage of this command is `grep -r "search string" directory/file_path`

The source where I learnt about this command was [this website](https://www.computerhope.com/unix/ugrep.htm) that explains many grep commands with detailed examples.

Following are some examples of `grep -r`'s usage. 

### Example 1: Using `grep -r` to find the word "Lucayans" within a repository of text files.[^1]
[^1]: This example is derived from my solution to the [skill demonstration](https://edstem.org/us/courses/31260/discussion/2510885).

<code><i>Input:</i> 
$ grep -r "Lucayans" written_2
<i>Output:</i> 
written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the <mark>Lucayans</mark>. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the <b>Lucayans</b>, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
</code>
