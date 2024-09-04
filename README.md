# Insertion-in-LinkedList-
Append method , prepend method , empty list and node creation
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None
        
        
class LinkedList:
    def __init__(self):
        self.head = None
        self.tail = None
        self.length = 0         
        
    def __str__(self):
        temp_node = self.head
        result = " "
        while temp_node is not None:
            result += str(temp_node.value)
            if temp_node.next is not None:
                result += " --> "
            temp_node = temp_node.next
        return result
        
    def append(self, value):
        new_node = Node(value)
        if self.head is None:
            self.head = new_node
            self.tail = new_node
        else:
            self.tail.next = new_node
            self.tail = new_node
        self.length += 1
    
    
    def prepend(self, value):
        new_node = Node(value)
        if self.head is None:
            self.head = new_node
            self.tail = new_node
        else:
            new_node.next = self.head
            self.head = new_node
        self.length += 1

        
   def insert(self, index, value):
       new_node = Node(value)
       temp_node = self.head
       for _ in range(index-1):
            temp_node = temp_node.next
       new_node.next = temp_node.next
       temp_node.next = new_node
       self.length += 1
        
        

          
          
new_linked_list = LinkedList()
new_linked_list.append(11)
new_linked_list.prepend(53)
new_linked_list.prepend(64)
new_linked_list.append(22)
new_linked_list.append(77)
new_linked_list.append(66)
new_linked_list.insert(3,66)

print(new_linked_list)
        
        
