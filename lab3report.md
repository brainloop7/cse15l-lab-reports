# Lab 3 Report
## Brian Liu CSE 15L 4:00 PM Thursdays

**grep**

Today I will be exploring the grep command. grep is a Bash command that is used for searching through files for certain patterns
of characters and then displaying the lines that contain the patterns.

Normally, grep is used something like this: 

```
$ grep "Indians" CH4.txt
```

In this command, I am using grep to search a text called CH4.txt for the string "Indians". If all runs as expected, all lines that include that string will be displayed.

Once I run the above command, this gets displayed to the terminal: 

```
Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize social norms and gain a sense of their future, of what they can become and how they can contribute to society.
```

As you can see, the line within the file CH4.txt that contained "Indians" was displayed. Although this grep command only showed one line, grep
will normally return ALL lines containing the associated string. 

Now that you understand how grep works, let's explore some alternatives! I found all of these alternatives here: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

**Alternative 1**

What if you only wanted to view the number of lines containing a string, rather than the lines themselves? To accomplish this, you can use the -c option, which
displays the number of lines containing a string. 

For example:

``` 
$ grep -c "Indians" CH4.txt
``` 

will output this:

```
1
```

Let's try searching for another string this time.

```
$ grep -c "Freud" CH4.txt
```

This is the output: 

```
4
```

This -c option is extremely useful in a variety of situations, especially in scenarios where you are required to count instances of something. For example,
just think about how useful it is when you press ctrl-f on a text file or on a website, and the number of matches is displayed. 

**Alternative 2**

Another very useful command for grep is -i. This command tells the terminal to ignore case as it searches for matching strings.

For example, you could run this:

```
$ grep -i "InDiAnS" CH4.txt
```

and still get all lines with the same character pattern, regardless of case. This is the output, which as you can see, matches with the output we got
when we used just "Indians" without -i

```
Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize social norms and gain a sense of their future, of what they can become and how they can contribute to society.
```

This could be also useful in situations where a word exists at the start of a sentence in some cases, because it will be capitalized and not capitalized sometimes.
Using -i, you should be able to find all instances regardless of capitalization. Here's an example:

``` 
$ grep -i "consistent" CH4.txt
```

outputs this:

``` 
The capacity to adopt a “theoretical” mode of reasoning in make-believe is highly consistent with Vygotsky’s belief that pretending assists children in separating mental syings in innovative ways. Reasoning about the nonreal is essential for abstract thinking and for many creative endeavors—that is, for human cognition to reach its highest po
Consistent with these all-too-familiar experiences, research conﬁrms that preschoolers are easily tricked by the outward appearance of things. They mistakenly conclude thatavell, Francis Green, and Eleanor Flavell presented children with appearance–reality problems in which objects were disguised in various ways. The children were asked what  When asked whether a white piece of paper placed behind a blue ﬁlter is “really and truly” blue or whether a can that sounds like a baby crying when turned over is “really
Recall from Chapter 3 that as children master puzzles and other problem-solving tasks, their self-guiding speech declines. Yet when graduate student Tina Gillingham and I othat private speech during make-believe remained uniformly high from ages 2 to 4 and actually increased at age 5.48 Our interpretation of the prevalence of private speech distent with Vygotsky’s theory, they create their own “zones,” frequently calling on self-directed language to work out their imaginings and bring behavior under the control
On a recent visit to my local library, I browsed the shelves devoted to biography, selecting several dozen life stories of accomplished writers, artists, and scientists. Thly years. Often a signiﬁcant person—a parent, an older sibling, or a relative—promoted imaginative experimentation and a sense of wonder by telling fantastic stories, initi
•Having fun. As illustrations of adult–child make-believe throughout this chapter affirm, most of the time parents and children engage in imaginative play just for fun. In 65 Consistent with this claim, participating in adult–child make-believe seems to precede children’s ﬁrst verbal jokes. One toddler named Ari, having become an avid make-ben a book his mother was reading to him, exclaimed “Neigh!” and laughed hysterically. At 21 months, while watching his mother wash dishes, he remarked, “Nutmeg [the family cumor makes plain, pretending is not just a pleasurable activity in itself but brings pleasure to life in general.
```

As you can see, all lines containing the word consistent, regardless of case, were displayed. As mentioned earlier, this can be very useful to account for
words being used in differing contexts, like at the start of sentences, when searching for words or phrases. 

**Alternative 3**

-n is also a very useful grep command. -n displays all matched lines, just like normal greps, in addition to their line numbers

For example, using the "Indians" example:

``` 
$ grep -n "Indians" CH4.txt
```

outputs:

```
37:Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize social norms and gain a sense of their future, of what they can become and how they can contribute to society.
```

As you can see, the command first displays the line number 37 before displaying the corresponding line.

Here's an example with multiple lines:

``` 
$ grep -n "Freud" CH4.txt
```

outputs:

```
32:Among inﬂuential explanations of why preschoolers are so drawn to pretending, Freud’s psychoanalytic theory and Piaget’s cognitive theory held sway for much of the twentieth century. Although each has made valuable contributions to our understanding, a new, more powerful view of the meaning of young children’s play has arrived on the scene, thanks to Vygotsky’s sociocultural theory.
36:Freud regarded make-believe play as a form of pleasurable wish fulﬁllment that allows children to act out uncertainties, anxieties, and hoped for outcomes and, therefore, to master frightening and frustrating events. Young children, Freud noted, often revisit anxiety-provoking experiences, such as a trip to the doctor’s office or discipline by a parent, but with roles reversed so the child is in command and compensates for unpleasant happenings. Sophie’s parents, aware of the previous day’s events, might have judged her pretend focus on bedtime, lollipops, and paciﬁers to contain at least an element of wish fulﬁllment. The evening before, they had told her, “Only one lolly from the candy dish,” and she had complained at having to go to bed while her parents continued to talk and laugh with their guests.
37:Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize social norms and gain a sense of their future, of what they can become and how they can contribute to society.
57:The widespread belief, originating with Freud, that play is pleasurable wish fulﬁllment characterizes certain playful pursuits—for example, acting out high-status roles, such as doctor, parent, or teacher, and thereby exercising authority over others instead of being directed and controlled. But not all fantasy qualiﬁes as wish fulﬁllment. In the sociodramatic scenarios that young children create, a doctor must have patients to inoculate, a parent must have children to discipline, and a teacher must have pupils to do assignments. Make-believe roles are not equally pleasurable—a feature of cooperation that is as true in everyday life as it is in fantasy play.
```

In this example, grep -n tells us that "Freud" appears in 32, 36, 37, and 57.

Ultimately, grep -n can be a super useful tool for anyone using Bash. An example of when it might be useful is when you're trying to cite a text and need the line
number. Using grep -n, you could search for a specific quote and find the corresponding line number for your citation.

**Alternative 4**

Lastly, another very useful grep command is grep -A n. This command allows you to print n lines after the result.

For example, 

```
$ grep -A 5 "Indians" CH4.txt
```

outputs the line with "Indians" and the next 5 lines as well.

```
Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize social norms and gain a sense of their future, of what they can become and how they can contribute to society.
Piaget’s View: Exercising a New Symbolic Capacity

Piaget acknowledged the emotional function of play, and he agreed that through pretending, children become familiar with social-role possibilities. But he is best known for stressing the symbolic nature of make-believe. Pretending, Piaget pointed out, is a vital means of mentally representing the world that, along with gestures, language, and drawings, develops rapidly in early childhood. Through it, children practice and strengthen their capacity to represent their experiences.3 For example, when Sophie pretended to put the animals to bed and used a TinkerToy to stand for a lollipop, she represented in her mind what formerly she could experience only directly—by going to bed or sucking a lollipop. Practicing and solidifying modes of representation, Piaget emphasized, make it possible for the child to free thought from the here and now; create larger images of reality that take into account past, present, and future; and transform those images mentally in the service of logical thinking.
Nevertheless, Piaget was convinced that by itself, make-believe play does little to advance children’s development. Rather, children merely exercise playfully the symbols they have acquired in other contexts.4 Much like his view of private speech as egocentric and nonsocial, Piaget believed that at ﬁrst pretend play is a solitary activity in which the child uses highly personal symbols that cannot easily be interpreted by others. Sociodramatic play, involving joint make-believe with a partner, Piaget claimed, is not under way until age 3. As with other aspects of Piaget’s theory, the direction of development for make-believe is from purely individual, egocentric symbols to social play and shared understanding.
Yet think back to 2-year-old Sophie’s pretending. Sophie is socially engaged throughout! From the start, she draws Kevin into the activity, explains her pretend actions so he can build on them, and responds cooperatively and appropriately to Kevin’s suggestions, as he does to hers. Vygotsky’s theory has been the wellspring of our recent appreciation of the profoundly social nature of even very young children’s imaginative play—and its wide-ranging inﬂuence on cognitive and social development.
```

Here's another example:

``` 
$ grep -A 1 "Freud" CH4.txt
```

which outputs:

```
Among inﬂuential explanations of why preschoolers are so drawn to pretending, Freud’s psychoanalytic theory and Piaget’s cognitive theory held sway for much of the twentieth century. Although each has made valuable contributions to our understanding, a new, more powerful view of the meaning of young children’s play has arrived on the scene, thanks to Vygotsky’s sociocultural theory.

--
Freud regarded make-believe play as a form of pleasurable wish fulﬁllment that allows children to act out uncertainties, anxieties, and hoped for outcomes and, therefore, to master frightening and frustrating events. Young children, Freud noted, often revisit anxiety-provoking experiences, such as a trip to the doctor’s office or discipline by a parent, but with roles reversed so the child is in command and compensates for unpleasant happenings. Sophie’s parents, aware of the previous day’s events, might have judged her pretend focus on bedtime, lollipops, and paciﬁers to contain at least an element of wish fulﬁllment. The evening before, they had told her, “Only one lolly from the candy dish,” and she had complained at having to go to bed while her parents continued to talk and laugh with their guests.
Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize social norms and gain a sense of their future, of what they can become and how they can contribute to society.
Piaget’s View: Exercising a New Symbolic Capacity
--
The widespread belief, originating with Freud, that play is pleasurable wish fulﬁllment characterizes certain playful pursuits—for example, acting out high-status roles, such as doctor, parent, or teacher, and thereby exercising authority over others instead of being directed and controlled. But not all fantasy qualiﬁes as wish fulﬁllment. In the sociodramatic scenarios that young children create, a doctor must have patients to inoculate, a parent must have children to discipline, and a teacher must have pupils to do assignments. Make-believe roles are not equally pleasurable—a feature of cooperation that is as true in everyday life as it is in fantasy play.
Even when make-believe does fulﬁll a child’s wishes, such pleasure is not unique to play. Many other activities, such as eating a favorite treat, being granted the undivided attention and affection of a parent, and listening to an exciting story, are at least as gratifying and sometimes more so than pretending. Indeed, imaginative wish fulﬁllment can, at times, be counterproductive. In well-known research on children’s ability to delay gratiﬁcation, psychologist Walter Mischel and his collaborators showed preschoolers some delicious marshmallows and told them that they could have one now or several if they waited until later. Children who spent the waiting period in a wish-fulﬁllment mode, thinking about what it would be like to eat those tasty marshmallows, were far less likely to wait patiently and successfully than children who turned their attention away from the treats and thought about other things.7 In this situation and others, being caught up in fantasized wish fulﬁllment interferes with attaining larger, more rewarding outcomes in real life—ones that would have been realized had the child been able to exercise imaginative self-restraint.
```

This could be very useful if you're looking for more context surrounding a word or phrase once you find it. For example, if you're searching for a word and are
interested in how the author develops their text afterwards, you could use -A n to expand what grep displays. 

**Summary**

Hopefully, you now understand the grep function and some of its important alternatives! Personally, just by researching and writing this lab report, I learned a lot
more about grep that I didn't know before and I hope I can apply this knowledge in the future. 
