#Lab 3 Report
##Brian Liu CSE 15L 4:00 PM Thursdays

** grep **

Today I will be exploring the grep command. grep is a Bash command that is used for searching through files for certain patterns
of characters and then displaying the lines that contain the patterns.

Normally, grep is used something like this: 

```
$ grep "Indians" CH4.txt
```

In this command, I am using grep to search a text called CH4.txt for the string "Indians". If all runs as expected, all lines that include that string will be displayed.

Once I run the above command, this gets displayed to the terminal: 

```
Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about 
themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; 
rabbit hunter and potter among the Hopi **Indians**; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small 
social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize 
social norms and gain a sense of their future, of what they can become and how they can contribute to society.
```

As you can see, the line within the file CH4.txt that contained "Indians" (marked in bold) was displayed. Although this grep command only showed one line, grep
will normally return ALL lines containing the associated string. 

Now that you understand how grep works, let's explore some alternatives! I found all of these alternatives here: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

** Alternative 1 **

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

** Alternative 2 **

