# Introduction:

Hello! My name is Dallin Howard, and my current task here, is to introduce you to a few new data sets, and how to use them, in an effective and proper manner. 
We'll be learning about **Stacks**, **Sets**, and **Trees**, each of which has different ways of storing data, and are helpful in their own ways, making each of them
more or less useful depending on how you want to store and unpack the data.

# Stacks

A stack is essentially a way of storing data that makes items to go in first the last things to come out of the storage. Think of it as a an empty tube of pringles, if you were to put a bbq chip in it would sit on the bottom, and if you were to put another cheddar chip in it would sit on top of the bbq chip. The only way to get the bbq chip would be to take out the cheddar chip that is on top of it. 
Thats is basically how a stack functions, the last item put in has to be the first item taken out, and the first item put in has to be the last out. 

Stacks can be useful in a few different ways a few common uses is that they can be used to reverse lists, store items or actions for an "undo" type feature, or be used as a way to recursively call a function. 


## Example

Below we have a simple example of using a stack

		#Create an empty list to use as a mystack
	mystack = []
		#adds some items to the stack
	mystack.append('1')
	mystack.append('B')
	mystack.append('3')
	mystack.append('D')

		#see all the items in the stack currently
	print(mystack) #['1', 'B', '3', 'D']

		#Prints the item at the end of the stack **AND** removes it
	print(mystack.pop()) #D

		#see the new stack
	print(mystack) #['1', 'B', '3']
	
		#Removes items, does NOT print
	mystack.pop()
	mystack.pop()
	
		#again prints the stack
	print(mystack) #['1']

Pay attention to how using the mystack.pop() both **removes** the item at the end of the stack **AND returns** it! 


## Try it

More or less that's the general basics of a stack! Below we have an example of a stack that needs some editing, right now it reads "['A', 'B', 'X', 'D', 'E', '100', 'F', 'G']" and our goal is to edit the stack to return as "['A', 'B', 'C', 'D', 'E', 'F', 'G']". We plan to do this by using another stack, to save items you'll need again in the future, and removing items you won't need again entirely. Copy paste below into an editor of your choice and give it a go, a solution will be provided if you get stuck. 
Remember: you can remove items completely just by using the .pop() function in it's own line, as shown in the previous examples

	#Create an empty list to use as a mystack
	mystack = ['A', 'B', 'X', 'D', 'E', '100', 'F', 'G']
	saveditems = []

	#Note you can move an item from one stack to another as follows
	saveditems.append(mystack.pop())
	
	#You can remove items completely just by using the .pop() function in it's own line, as shown in the previous examples
	
	#Input code below to edit the stacks provided using the .pop() and .append() functions. 
	
	
	#No need to change anything below this
	print(f"Current stack: {mystack}") #In the end it should return "['A', 'B', 'C', 'D', 'E', 'F', 'G']"
	print(f"Currently saved items: {saveditems}") #used for you to see what items have been saved to your saved items stack.


Below we have a provided solution, yours still may look somewhat different


<details>
  <summary>Solution Provided</summary>

  ```
	
	#Create an empty list to use as a mystack
	mystack = ['A', 'B', 'X', 'D', 'E', '100', 'F', 'G']
	saveditems = []

	#Note you can move an item from one stack to another as follows
	saveditems.append(mystack.pop())
	
	#You can remove items completely just by using the .pop() function in it's own line, as shown in the previous examples
	
	#Input code below to edit the stacks provided using the .pop() and .append() functions. 
	saveditems.append(mystack.pop())
	mystack.pop()
	saveditems.append(mystack.pop())
	saveditems.append(mystack.pop())
	mystack.pop()
	mystack.append('C')
	mystack.append(saveditems.pop())
	mystack.append(saveditems.pop())
	mystack.append(saveditems.pop())
	mystack.append(saveditems.pop())
	
	#No need to change anything below this
	print(f"Current stack: {mystack}") #In the end it should return "['A', 'B', 'C', 'D', 'E', 'F', 'G']"
	print(f"Currently saved items: {saveditems}") #used for you to see what items have been saved to your saved items stack.
	
  ```
</details>

# Sets

## What it is and how it functions 

Sets are a common data structure used to store multiple items into one variable, a couple of key things to take note of are that sets are unordered, variables can't be changed (only added or removed), and can't have the duplicates of an item in the set.

If a set is way more restrictive than a list then why use a set? Well that's pretty simple, since sets don't have distinctive indexes they only care about if an individual item is in the set, and are extremely efficient in locating items within them at an algorithm efficiency of O(1), making finding an item in a 1000 item data structure incredibly efficient, vs a list individually iterating through each item in it's library. 

A list can be constructed as follows

	myList = ['A', 1, 'C', 'D', 'E', True, 'A', 'B', 'C', 'D', 'E', 'F']
	
Note the square brackets, in comparison to a dictionary as seen below

	mySet = {'A', 1, 'C', 'D', 'E', True, 'A', 'B', 'C', 'D', 'E', 'F'}
	
Again take note in the bracket types used. The brackets used initialize a dictionary type set, which has all the same general traits of a set. (No duplicates, can't edit items in the set, and unordered) Alternatively you can avoid initializing a dictionary you can create an empty set as follows:

	mySet = set()
	
To create a set with items already within it take a look at this. 

	mySet = set(('A', 1, 'C', 'D', 'E', True, 'A', 'B', 'C', 'D', 'E', 'F'))

Make a note of the extra () adding in the items, this is required for adding in items on initialization.


If you were to execute print statement for an identical list and set, the difference would be that the set would not return the duplicates, and be scrambled in a random order. Your program would run and ignore the duplicates in the set, leaving you with just one item for each value.

	mySet = {'A', 1, 'C', 'D', 'E', 'F', True}
	
Lastly sets are very similar to simple lists in many regards in terms of functionality,  minus the ability to work with index numbers. You can add or remove items in the set with a few simple commands

	#add an item to a set with
	mySet.add('item')
	
	#remove from sets with
	mySet.remove(1)

## Try

That's the basics about sets! Below we have some test code for you to work with. The goal of the code is for you to make the set "mySet" identical to the list "myList". This can be done a number of ways, find what works for you. Do not create any new sets or lists for this task.

	myList = ['A', 1, 'C', 'D', 'E', 'A', 'B', 'C', 'D', 'E', 'F']
	mySet = set(("Number", "X", 35, "S"))
	removal = []
	
	
	#Add your code here





	#Code below is to check your progress, no need to change anything
	finder = []
	for listitem in myList:
	    if listitem not in mySet:
	        finder.append(listitem)
	    else:
	        removal.append(listitem)
	print(f"Failed to find the following items {finder}")
	for item in removal:
	    if item in mySet:
	        mySet.remove(item)
	
	finder = []
	if len(mySet) == 0:
	    print("Set reassigned successfully")
	else:
	    for itemleftinset in mySet:
	        finder.append(itemleftinset)
 	   print(f"Additional items found {finder}")

While updating your lists to sets might seem like a waste of time and effort, in the long game this would be an efficient way to locate items as the efficiency of a set is O(1), creating an overall more efficient program! 

Below is a simple solution for the code above.

<details>
  <summary>Solution Provided</summary>

  ```
	myList = ['A', 1, 'C', 'D', 'E', 'A', 'B', 'C', 'D', 'E', 'F']
	mySet = set(("Number", "X", 35, "S"))
	removal = []
	
	
	#Add your code here
	for setitems in mySet:
	    removal.append(setitems) #saves items currently in set to be removed

	for i in removal: #checks each item in the removal list, and removes them if they're present
	    if i in mySet:
        	mySet.remove(i)

	for listitems in myList: #iterates through the list and adds the items to the set
	    mySet.add(listitems)

	#Code below is to check your progress, no need to change anything
	finder = []
	for listitem in myList:
	    if listitem not in mySet:
	        finder.append(listitem)
	    else:
	        removal.append(listitem)
	print(f"Failed to find the following items {finder}")
	for item in removal:
	    if item in mySet:
	        mySet.remove(item)
	
	finder = []
	if len(mySet) == 0:
	    print("Set reassigned successfully")
	else:
	    for itemleftinset in mySet:
	        finder.append(itemleftinset)
 	   print(f"Additional items found {finder}")
	
  ```
</details>
