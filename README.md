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



# Trees

A tree (or binary tree) is a rather interesting data structure storing data in a stucture similar to a tree, with a main root, and branches coming off of that root, and more branches from the branches, that continues until all the data you have is stored at the end of a branch. These trees are extremely effective at storing large amounts of data into a single variable, and can be be called recursively to locate specific data from within them. 

If we break down a tree to it's simplest parts, we really only have three items to work with, the "node" (or current data), with a left child, and a right child. Simply put trees can have dozens or hundreds of individual nodes, each with their own children elements. The node that everything stems from is called the "root". 

## How to create a tree

Before we get into things take a look at the code below to create a Node, this will be used inside the tree to create the nodes where data is stored.

	class Node:
		def __init__(self, data=None):
			self.data = data
			self.left = None
			self.right = None


Simply put you create a class for the creation of nodes to start things off in the "class Node" definition, which will then create the links to its "left" and "right" child elements. If there is data to store, it will also be found in the node. 

Below we have the creation of the tree itself, along with a function to add nodes into the tree. The comments here can be helpful to explain in the moment.


	class Tree:
	    def __init__(self):
		self.root = None

	    def insert(self, data):
		if self.root is None:
		    self.root = Tree.Node(data)
		else:
		    self._insert(data, self.root)  #Calls the insert function


	    def _insert(self, data, node):
	    	#if the node is less than the parent item places on the left side
		if data < node.data:
		    # Checks for a left node
		    if node.left is None:
			#No left item
			node.left = Tree.Node(data)
		    else:
			# Calls this function again to search for a different position that fits
			# By traveling farther into the tree
			self._insert(data, node.left)
		elif data == node.data:
		    #skips the node if its a duplicate
		    pass
		else:
		    #if node is greater than it's parent item places it on the right side
		    if node.right is None:
			# No node on the right side, so it places
			node.right = BST.Node(data)
		    else:
			# Calls this function again to search for a different position that fits
			# By traveling farther into the tree
			self._insert(data, node.right)

Looking at the tree we have established the use of this one is to store numbers. Bigger numbers on the right side of the tree and smaller numbers on the left side of the tree.

<details>
  <summary>Full tree create w/ node here</summary>

  ```
	class Tree:
		class Node:
			def __init__(self, data=None):
				self.data = data
				self.left = None
				self.right = None
	    def __init__(self):
		self.root = None

	    def insert(self, data):
		if self.root is None:
		    self.root = Tree.Node(data)
		else:
		    self._insert(data, self.root)  #Calls the insert function


	    def _insert(self, data, node):
	    	#if the node is less than the parent item places on the left side
		if data < node.data:
		    # Checks for a left node
		    if node.left is None:
			#No left item
			node.left = Tree.Node(data)
		    else:
			# Calls this function again to search for a different position that fits
			# By traveling farther into the tree
			self._insert(data, node.left)
		elif data == node.data:
		    #skips the node if its a duplicate
		    pass
		else:
		    #if node is greater than it's parent item places it on the right side
		    if node.right is None:
			# No node on the right side, so it places
			node.right = BST.Node(data)
		    else:
			# Calls this function again to search for a different position that fits
			# By traveling farther into the tree
			self._insert(data, node.right)
	
  ```
</details>

With that all you'd have to do is add in the nodes into your tree! This would be done easily throught the following commands

	root = Tree()
	root.insert(12)

Simple now right? Initialize the root item, then from there on the rest of the items will sort themselves into the tree, for example if we were to add in a few more items with the following commands

	root.insert(18)
	root.insert(27)
	root.insert(7)
	root.insert(2)
	root.insert(5)
	root.insert(22)
	
With that we have our basic tree that would look similar to this if drawn on paper
	
									 12
								      /     \
								    7          18
								  /   \      /    \
								 2     5    22      27
								 


With that that's the basics of creating and adding to a tree. There are a few ways of creating trees in python, all of which are similar in accomplishing the same task, but different in overall excecution. Many tree's might not have data in all nodes on the tree as well, such as a "huffman coding" type tree, which is a way of binary compression using one of these trees.

## Try this out

Huffman coding, is a form of binary compression that uses the amount of times a letter or symbol appears to create a most data efficient way of storing those characters. For example the string "That's pretty cool" has the letter T appear 4 times, O appears, twice, and the other characters and symbols once. So the process would store the Ts as the smallest number (or highest up on the tree) and the Os with the next priority. Matching characters are typically sorted by first appearance, so H would be next placed on the tree. The way the tree is created is by how often the items appear vs the total amount of characters in the string. [This Website](https://cmps-people.ok.ubc.ca/ylucet/DS/Huffman.html) can break down exactly how things will be assembled in the end tree! Try the website with the following strings 
	
	what time is it
	she sells sea shells by the sea shore
	the quick black fox jumps over the lazy dog

Note that this is the final product of what the tree holds, but the only things that are important are the end branches or "leaves" with the letters and the occurence counts. 

Below we have a code of a basic huffman coding compressor. 

<details>
  <summary>huffman problem</summary>

  ```

	string = 'BCAADDDCCACACAC'
	string = string.lower()

	# Creating tree and makes function for readies for creating the nodes (children)
	class NodeTree(object):
	    def __init__(self, left=None, right=None):
		self.left = left
		self.right = right

	# Calculates each items occurence in the string
	quantity = {}
	for letter in string:
	    if letter in quantity:
		quantity[letter] += 1
	    else:
		quantity[letter] = 1
	quantity = sorted(quantity.items(), key=lambda x: x[1], reverse=True)
	occurence = quantity

	#This calculates how often a letter or symbol shows up in the string
	while len(occurence) > 1:
	    (key1, c1) = occurence[-1]
	    (key2, c2) = occurence[-2]
	    occurence = occurence[:-2]
	    node = NodeTree(key1, key2)
	    occurence.append((node, c1 + c2))
	    occurence = sorted(occurence, key=lambda x: x[1], reverse=True)



	# Main function that creates the tree
	def binarytree(node, binarystring=''):
	    if type(node) is str:
		return {node: binarystring}
	    data = dict()

	    ###add in the updates to the the nodes below, 
	    ###(hint: each node in this method of a tree uses a dictionary to see it's children, and that recursion is useful here)
	    ### binarystring is the parent nodes binary number
	    return data

	
	huffmanCode = binarytree(occurence[0][0])

	print(' Char | Example binary')
	print('----------------------')
	for (letter, quant) in quantity:
	    print(' %-4r |%12s' % (letter, huffmanCode[letter]))

	print()
	  ```
</details>

Be sure to think about how the data is stored, and about how you might recursively call into the tree to add items. 

end product should be as follows: 
	'c'  |           0
 	'a'  |          11
 	'd'  |         101
 	'b'  |         001
	
<details>
  <summary>Solution Provided</summary>

  ```

	string = 'BCAADDDCCACACAC'
	string = string.lower()

	# Creating tree and makes function for readies for creating the nodes (children)
	class NodeTree(object):
	    def __init__(self, left=None, right=None):
		self.left = left
		self.right = right


	# Calculates each items occurence in the string
	quantity = {}
	for letter in string:
	    if letter in quantity:
		quantity[letter] += 1
	    else:
		quantity[letter] = 1
	quantity = sorted(quantity.items(), key=lambda x: x[1], reverse=True)
	occurence = quantity

	#This calculates how often a letter or symbol shows up in the string
	while len(occurence) > 1:
	    (key1, c1) = occurence[-1]
	    (key2, c2) = occurence[-2]
	    occurence = occurence[:-2]
	    node = NodeTree(key1, key2)
	    occurence.append((node, c1 + c2))
	    occurence = sorted(occurence, key=lambda x: x[1], reverse=True)



	# Main function that creates the tree
	def binarytree(node, binarystring=''):
	    if type(node) is str:
		return {node: binarystring}
	    data = dict()

	    ###add in the updates to the the nodes below, 
	    ###(hint: each node in this method of a tree uses a dictionary to see it's children, and that recursion is useful here)
	    ### binarystring is the parent nodes binary number
	    data.update(binarytree(node.right, '1' + binarystring))
	    data.update(binarytree(node.left, '0' + binarystring))
	    return data


	huffmanCode = binarytree(occurence[0][0])

	print(' Char | Example binary')
	print('----------------------')
	for (letter, quant) in quantity:
	    print(' %-4r |%12s' % (letter, huffmanCode[letter]))

	print()
	
  ```
</details>

# Conclusion
That's a basic crash course on three different types of data structures! These all have their own separate uses, and are all helpful in their own ways, when creating a project think about which might be the most beneficial and efficient for your team and project!
