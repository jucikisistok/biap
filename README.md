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
The reason why we use functions is because writing down the same thing over and over again is not only frustrating, but also fairly detrimental in terms of productivity. This is how an average function looks like:  

![Functions](https://github.com/jucikisistok/biap/blob/master/figures/fig_15.png)  
*The anatomy of a simple function.*

For example, whenever we need a function to divide two numbers, we can call my_function the following way:

![Functions](https://github.com/jucikisistok/biap/blob/master/figures/fig16.png)  
*Calling a function and storing the result in a variable.*

In this example, we also store the result (aka the stuff that the function returns) in a variable called divide, so we can reuse this value later. This example illustrates it very well that we need to keep track of what our arguments are and what their correct order is – for example, if we want to calculate what 7 divided by 5 is, we need to specify 7 as our first argument and 5 as our second argument, otherwise we get 5/7. This type of bug is exceptionally dangerous – it’s easy to get caught up in the joy of writing a program that works, but if we aren’t careful, the results can lead us astray. 

Also, we need to be careful of what kind of data type we use – since division makes sense in terms of integers and floats, if we pass in something else, like strings or dictionaries, we won’t have a particularly good time. (Unless you’re into errors, that is.)

No matter how long or complicated a function is, the result that you can extract from it is something that is written next to **the very first return statement the program encounters**. This is why you need to be extremely careful about where you put it – the wrong placement can easily result in faulty outputs. Let’s say you want to see whether there are odd numbers in a list, so you write code like this:

![Functions](https://github.com/jucikisistok/biap/blob/master/figures/fig17.png)  
*This returns False.*

This function will return False, which is obviously not the right result. Since both return statements are inside the for loop, what will happen here is that the function looks at the very first number, in this case 4, and returns something (in this case, False). However, what you really want is this:

![Functions](https://github.com/jucikisistok/biap/blob/master/figures/fig18.png)  
*This returns True.*

The difference is subtle, but very powerful. In this case, we have the second return statement outside of the for loop – essentially, we say that okay, let’s iterate through all the list and only return True if there is an odd number there – otherwise, once we finished with looking through the entire list but haven’t found any odd numbers, let’s return False.

The biggest strength of functions is that they are **highly reusable** – hence, hard-coding values into them leads to bad karma, unwanted surprises and (potentially) banging your head against the table. Let’s see an example:

![Functions](https://github.com/jucikisistok/biap/blob/master/figures/fig19.png)  
*This returns (True, [4, 5, 9, 2])*

See what’s wrong here? We essentially wrote a function that’s only good for one thing – analysing the [4, 5, 9, 2] list, no matter if we try to call it with a different argument later. Moral of the story: never define anything inside the function that should be passed in as an argument. 

<h2>Calling functions inside other functions</h2>
As I mentioned earlier, the magic of functions is in the reusability – and in fact, you can absolutely benefit from a function inside another function (this is also called “not reinventing the wheel”). If you think about a function in terms of the value it returns, and not the series of steps that need to be taken to get to that value (or the blood, sweat and tears you put into constructing those steps), then it becomes fairly straight-forward.  
Let’s see an example:

![Functions](https://github.com/jucikisistok/biap/blob/master/figures/fig20.png)  
*Returns "Northern downpour sends its love”. Sweet.*

In this case, we use the odd function to “help out” pretty_odd. Since number_list indeed has odd numbers, is_it_odd = odd(nr_list) is essentially is_it_odd = True. Of course, there is no point in writing two separate functions to achieve this exact functionality, but it was a simple way to illustrate my point :)  

The arguments should only match up within a function (but make no mistake, there they should definitely match up). If I want, I can call the argument of pretty_odd something other than nr_list, I just need to be careful to use it when I call odd inside pretty_odd. Just like this:

![Functions](https://github.com/jucikisistok/biap/blob/master/figures/fig21.png)  
*This is exactly the same as the previous one.*

<h2>How to debug</h2>
It can often happen that your code is not behaving like it should – you either don’t get the right results, or you get an error, plain and simple. In such cases it’s always a good idea to go ahead and comment things out – it helps you to pinpoint where your code goes wrong. Also, there is no shame in printing – quite the contrary – it is extremely helpful when it comes to understanding what your script actually does.  

In fact, whenever you need to write some code, it’s highly recommended to write a couple of lines and print the results. Sure, it might slow you down a bit, but it’s still less time-consuming than trying to find a little typo or indentation problem in 50 (or 500) lines of code :)    
