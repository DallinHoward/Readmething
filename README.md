# Introduction:

Hello! My name is Dallin Howard, and my current task here, is to introduce you to a few new data sets, and how to use them, in an effective and proper manner. 
We'll be learning about **Stacks**, **Sets**, and **Trees**, each of which has different ways of storing data, and are helpful in their own ways, making each of them
more or less useful depending on how you want to store and unpack the data.

## Stacks

A stack is essentially a way of storing data that makes items to go in first the last things to come out of the storage. Think of it as a an empty tube of pringles, if you were to put a bbq chip in it would sit on the bottom, and if you were to put another cheddar chip in it would sit on top of the bbq chip. The only way to get the bbq chip would be to take out the cheddar chip that is on top of it. 
Thats is basically how a stack functions, the last item put in has to be the first item taken out, and the first item put in has to be the last out. 

Stacks can be useful in a few different ways a few common uses is that they can be used to reverse lists, store items or actions for an "undo" type feature, or be used as a way to recursively call a function. 


### Example

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


### Try it

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
