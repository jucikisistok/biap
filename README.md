<h2 style = "text-align: center !important;"><center>A guide to solving any problem ever & understanding what your code actually does (as opposed to what you thought it does)  </h2> </center>
  <h4><center>Judit Kisistók<center> (<a href = "mailto:judit.kisistok@gmail.com">judit.kisistok@gmail.com</a>)</h4> <hr />

1.	Don’t write code yet! As the ancient Egyptians used to say, writing a bunch of code before thinking through the problem and just praying to the programming gods while hoping that something good will come out of that mess is very bad news.
2.	Break up the problem into smaller, manageable parts.
3.	Think about how you would solve a given subproblem with your human brain – if you are completely clear about what needs to happen and you’re able to systematically think through every single step, it’s much easier to trick Python into doing what you want it to do.
4.	Now, write some code.
5.	When in doubt, print! No, seriously, printing is our best friend. Not sure what that variable means? Print it. Not sure how your for loop works? Print it. It’s extremely important to understand what your code does – and oftentimes, it’s useful to see it to believe it.
6.	Debugging. Test your code as often as humanly possible – again, printing is a great way to do so. Once you’ve finished a function, try it on different inputs to see if it works as expected. [Optional: <a href="https://rubberduckdebugging.com/">get a rubber duck</a> and start debugging like a true pro.]
7.	Rinse and repeat.
8.	Celebrate your Master Problemsolver status. It’s pretty impressive.

Now, for the practical part – it’s not too hard to get lost in the deep, dark forest of different loops, if statements, lists, dictionaries, dictionaries in dictionaries, dictionaries in dictionaries in dictionaries, and so on. Here is a quick overview of some syntax, terminology and explanations that I put together based on your questions so far – an FAQ, if you will.

<h2>Getting a particular character from a string or an element from a list (indexing)</h2> 
Let’s revise the syntax for string and list indexing. This is how it goes:

![String and list indices - forwards and backwards](https://github.com/jucikisistok/biap/blob/master/figures/fig1.png)
*String and list indices - forwards and backwards*

<h2>Slicing strings / obtaining a range of elements from a list</h2>
Now we are super clear about indexing, but we suddenly find ourselves in a sticky situation where we need to extract a range of characters from a string, or a range of elements from a list. So, how do we do that?

![Slicing](https://github.com/jucikisistok/biap/blob/master/figures/fig2.png)
*Slicing*

<h2>The anatomy of a for loop</h2>
It’s important to note that there is absolutely nothing special about i. In fact, the following two for loops do exactly the same, one of them is just more painful to look at:

![For loops](https://github.com/jucikisistok/biap/blob/master/figures/fig3.png)  
*Both of these print 1, 5, 2, 3 and “python”.*

In this case, python looks at the list itself, and substitutes i (or, y’know, justinbieber) to the value that it finds in the list. However, let’s take a look at this:

![For loops](https://github.com/jucikisistok/biap/blob/master/figures/fig4.png)  
*This is fundamentally different - both of these print 0, 1, 2, 3, 4.*

In this second case, what’s in the function doesn’t matter at all. The length of our list is 5, and range(5) is the range between 0 and 5, hence, the values from 0 to 4 will be printed as the end of the range is exclusive.

Let’s twist this once more. What if you want to get the value from a list, but the only thing you now is that you want to access it by its index? Well, you do the following:

![For loops](https://github.com/jucikisistok/biap/blob/master/figures/fig5.png)  
*This again prints 1, 5, 2, 3 and "python" - note that it is equivalent to the for loops that gave the same results before!*

Okay, what’s going on here? As we discussed, we look at all i’s in the range of 5, so the iterations go like i = 0, i = 1, etc., and in every single iteration, we access the element in the list that is at that particular index, so in the first iteration, when i = 0, my_list[0] = 1, so this is what gets printed, and so on.

<h2>Iterating through a dictionary</h2>

The basic anatomy of a dictionary is that it has keys and corresponding values. If you want to iterate through a dictionary, you might write code like this:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig6.png)  
*This will print TTT, TTC, TTA.*

What happens in this case is that python thinks that you want to iterate through the keys – so it gives you those. However, sometimes you want to iterate through the values, which can be achieved by a rather simple modification:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig7.png)  
*This prints F, F, L.*

Not a huge fan of the .values() method? Good news – you don’t absolutely have to use it. In fact, this code gives you the exact same result:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig8.png)  
*This, again, prints F, F, L.*

What happens here? We look into our dictionary, and want to find the value that is at that particular key we’re currently looking at. Let’s see it in detail:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig9.png)  
*A high-level overview of iterations in dictionaries.*

<h2>Dictionaries of dictionaries</h2>

We only need to take this one step further to be able to deal with dictionaries in dictionaires. Let’s look at a dictionary similar to the overlap one in the assignment: 

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig10.png)  
*A dictionary in a dictionary.*

What if we want to obtain the value of an overlap? We need to get inside the inner dictionary and get the value that we need from there. This is how:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig11.png)  
*Getting a value from the inner dictionary.*

If you want to add a new key-value pair to the dictionary, it goes pretty similarly.

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig12.png)  
*This will add a brand-new key-value pair to your dictionary.*

Maybe at some point you realize that a mistake has been made and you want to change a value, for example, the Read1-Read2 overlap is not 17, but 55. You can simply write this:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig13.png)  
*Updating values in your inner dictionary.*

When throwing loops in the mix, the most important thing is to remember what you’re actually iterating through – the keys or the values? [If you’re unsure, please refer back to Figures 6-8.]

It might happen that you only want to iterate through certain key-value pairs – for example, someone gave you a list with the relevant reads. What you do then is the following:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig14.png)  
*Getting the relevant reads. Prints {'Read2': 5, 'Read3': 9} and {'Read1': 3, 'Read3': 15}.*

Here’s what’s going on – in the first line of the for loop you say that you want to iterate through the elements in the list, so read is going to be Read1 in the first iteration and Read2 in the second iteration. In the second line, you will take that element from the list and use it as a key – for example, in the first iteration read is Read1, so dic2[read] is actually dic2[Read1], which is {'Read2': 5, 'Read3': 9}.
Of course, this only works if the dictionary has all the keys that the list specifies, but if it doesn’t, you can just write code like this to deal with that situation:

![Dictionaries](https://github.com/jucikisistok/biap/blob/master/figures/fig15.png)  
*Prints {'Read2': 5, 'Read3': 9}, {'Read1': 3, 'Read3': 15} and :(.*

<h2>The anatomy of a function</h2>
Coming soon.

<h2>Calling functions inside other functions</h2>
Coming soon.

<h2>How to debug</h2>
Coming soon.
