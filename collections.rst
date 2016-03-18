--------------------------
Collections : Java to Apex
--------------------------
Table of Contents
=================
1. `Table of Summary`_
2. `Collections`_
      - `List`_
         - `Accessing Elements in List`_
      - `Set`_
         - `Accessing Elements in Set`_
      - `Map`_
         - `Accessing Elements in Map`_
3. `References`_
4. `Summary`_

Table of Summary
================

+--------------+-----------------------------+-----------------+----------------------------+ 
|              |          Java               |       Apex      | Remarks                    |
+==============+=============================+=================+============================+
|Collections   | Supported through a set of  |No interfaces    | No limit for size, but     |                      
|              | interfaces.                 |                 | apex counts for heap size  |                         
+--------------+-----------------------------+-----------------+----------------------------+ 
| List         |Uses the below Interfaces    | Uses the methods|                            | 
|              | - java.util.ArrayList       | in the List     |                            | 
|              | - java.util.LinkedList      | class           |                            |
|              | - java.util.Vector          |                 |                            |   
|              | - java.util.Stack           |                 |                            |   
+--------------+-----------------------------+-----------------+----------------------------+ 
| Set          |Uses the below Interfaces    | Uses the methods|Unlike Java, apex developers|                          
|              | - java.util.EnumSet         | in the Set class|don't need to reference the |                            
|              | - java.util.HashSet         |                 |algorithm to implement a set|                           
|              | - java.util.LinkedHashSet   |                 |in the declarations( for eg.|                           
|              | - java.util.TreeSet         |                 |HashSet or TreeSet).        |
|              |                             |                 |Apex uses Hash structure for|
|              |                             |                 |sets.                       |
+--------------+-----------------------------+-----------------+----------------------------+ 
| Map          |Uses the below Interfaces    | Uses the methods|Unlike Java, apex developers|                            
|              | - java.util.HashMap         | in the Set class|don't need to reference the |                          
|              | - java.util.Hashtable       |                 |algorithm to implement a set|                            
|              | - java.util.IdentityHashMap |                 |in the declarations(for eg. |                            
|              | - java.util.LinkedHashMap   |                 |HashMap or TreeMap).        |                     
|              | - java.util.Properties      |                 |Apex uses Hash structure for|                          
|              | - java.util.TreeMap         |                 |Maps                        |  
|              | - java.util.WeakHashMap     |                 |                            |
+--------------+-----------------------------+-----------------+----------------------------+

Collections
===========
  
Java
^^^^
A Java collection can store data of different types in a single structure and be sized dynamically (allowed to grow or shrink). The collections in Java are primarily supported through a set of interfaces.

The Java collections framework defines several interfaces as below:

- The Collection Interface
- The List Interface
- The Set Interface
- The Map Interface
- The Queue Interface
- The Deque Interface
- The SortedSet Interface
- The SortedMap Interface

Apex
^^^^

Collections are the variables that can store numerous records of any datatype. There is no limit on the number of items a collection can hold. However, there is a general limit on `heap size`.

Apex has three  types of collections.

* :code:`List`
* :code:`Set`
* :code:`Map`

List
===============

Java
^^^^
The List interface extends Collection and declares the behaviour of a collection that stores a sequence of elements.

The :code:`java.util.List` interface is a subtype of the :code:`java.util.Collection` interface. It represents an ordered list of objects, meaning you can access the elements of a List in a specific order, and by an index also. 

Since List is an interface you need to instantiate a concrete implementation of the interface in order to access it. You can choose between the following List implementations from the Java Collections API:

* :code:`java.util.ArrayList`
* :code:`java.util.LinkedList`
* :code:`java.util.Vector`
* :code:`java.util.Stack`

Below are few examples for creating the List instance:

.. code-block:: java

   List listA = new ArrayList();
   List listB = new LinkedList();
   List listC = new Vector();
   List listD = new Stack();

Apex
^^^^
A `list` is an ordered collection of elements that are accessed by their indices. List elements can be of any data type—primitive types, sObjects, user-defined types, built-in Apex types or other collections. The index position of the first element in a list is always 0.

Use a `list` when the sequence of elements is important. There can be duplicate elements in a list. You have to use :code:`List` keyword followed by the datatype of the variables within the < > characters. 

*Syntax*

.. code-block:: java

   List<datatype> my_list = new List<datatype>(); 
   List<datatype> my_list1 = new List<datatype>{value1, value2, ..};  

Lists can contain any collection and can be nested within one another and thus becomes multidimensional list. A list can contain up to four levels of nested collections inside it, that is, a total of five levels overall.  For example, you can have a list of lists of sets of Integers.

*Example*

.. code-block:: java

   // Create a nested list
   List<List<Set<Integer>>> my_list_2 = new List<List<Set<Integer>>>();   


*************************************
Accessing Elements in List
*************************************
Java
^^^^
*Example*
 
.. code-block:: java

   List listA = new ArrayList();
   listA.add("element 1");
   listA.add("element 2");

   // gets the element at index 0
   String s = listA.get(0);  

   //Removes all the elements from the list
   listA.clear();  

   //results the size of the list 
   listA.size();     

Apex
^^^^
To access the elements in the list, use :code:`list` methods provided by apex.

*Example*
 
.. code-block:: java

   List<String> myList = new List<String>(); 

   // Adds a element of value "element 1" to the end of the list
   myList.add("element 1");        
   myList.add("element 2");

   // Retrieves the element at index 0
   String s = myList.get(0);       
   myList.set(0, "element 3"); 

   // Removes all elements from the list
   myList.clear();  

   // Returns the size of the list               
   myList.size();                  


Set
===
Java
^^^^
Sets are unordered and so cannot contain duplicates of the same element. Implemented by the HashSet class.

The :code:`java.util.Set` interface is a subtype of the :code:`java.util.Collection` interface. It represents set of objects, meaning each element can only exists once in a Set.

Since Set is an interface you need to instantiate a concrete implementation of the interface in order to use it. You can choose between the following Set implementations in the Java Collections API:

* :code:`java.util.EnumSet`
* :code:`java.util.HashSet`
* :code:`java.util.LinkedHashSet`
* :code:`java.util.TreeSet`

Below are the few examples:

.. code-block:: java

   Set setA = new EnumSet();
   Set setB = new HashSet();
   Set setC = new LinkedHashSet();
   Set setD = new TreeSet();

Apex
^^^^
A set is an unordered collection of elements that do not contain any duplicates. Set elements can be of any data type—primitive types, sObjects, user-defined types, built-in Apex types or other collections.

To declare a set, use the :code:`Set` keyword followed by the primitive data type name within <> characters. 

*Syntax*

.. code-block:: java

   Set<datatype> my_set = new Set<datatype>();
   Set<datatype> my_set1 = new Set<datatype>{value1, value2, ..};

Sets can contain collections that can be nested within one another. 

*Example*

.. code-block:: java

   // Defines a new set with two elements
   Set<String> s1 = new Set<String>{'a', 'b + c'}; 
   // Defines a new set that contains the elements of the set created in the previous step
   Set<String> s2 = new Set<String>(s1); 

***************************
Accessing Elements in Set
***************************
Java
^^^^   
*Example*
 
.. code-block:: java    
 
   //Creates a new Set   
   Set setA = new HashSet();
   //Adds values to the set
   setA.add("element 1");
   setA.add("element 2");
   //Removes the value "element 1" from the set
   setA.remove("element 1");
   //Removes all the elements from the set
   setA.clear();     
   //results the size of the set 
   setA.size();                                

Apex
^^^^

To access elements in a set, use the system methods provided by Apex.

*Example*

.. code-block:: java

   // Define a new set
   Set<String> s = new Set<String>(); 
   
   // Add an element to the set
   s.add("element 1"); 
   s.add("element 2");        
  
   // Remove the element from the set 
   s.remove("element 1");  
  
   //Removes all the elements from the set
   s.clear();     
  
   //results the size of the set 
   s.size();                      
  

Map
===============
Java
^^^^   
Maps store objects based on the values of unique key-value associations between objects.A map can store duplicate objects, but not with duplicate keys.

The :code:`java.util.Map` interface represents a mapping between a key and a value. The Map interface is not a subtype of the Collection interface.

Since Map is an interface you need to instantiate a concrete implementation of the interface in order to use it. You can choose between the following Map implementations in the Java Collections API:

* :code:`java.util.HashMap`
* :code:`java.util.Hashtable`
* :code:`java.util.EnumMap`
* :code:`java.util.IdentityHashMap`
* :code:`java.util.LinkedHashMap`
* :code:`java.util.Properties`
* :code:`java.util.TreeMap`
* :code:`java.util.WeakHashMap`

Below are few examples of how to create a Map instance:

.. code-block:: java

   Map mapA = new HashMap();
   Map mapB = new TreeMap();

Apex
^^^^
A map is a collection of key-value pairs where each unique key maps to a single value. Keys and values can be any data type—primitive types, sObjects, user-defined types, built-in Apex types or other collections.

To declare a map, use the Map keyword followed by the data types of the key and the value within <> characters.

*Example*

.. code-block:: java

   Map<datatype,datatype> my_map = new Map<datatype,datatype>();

Map keys and values can contain any collection, and can contain nested collections. For example, you can have a map of Integers to maps, which, in turn, map Strings to lists. Map keys can contain up to only four levels of nested collections.

*Example*

.. code-block:: java

   Map<ID, Set<String>> m = new Map<ID, Set<String>>();

***************************
Accessing Elements in Map
***************************
Java
^^^^   
*Example*
 
.. code-block:: java 

   Map mapA = new HashMap();
   //maps a string value "element 1" to a string key "key1"
   mapA.put("key1", "element 1");
   mapA.put("key2", "element 2");
  
   // get the value based on the key
   String element1 = (String) mapA.get("key1"); 
   //remove the value from the map
   mapA.remove("key1");

Apex
^^^^
*Example*

.. code-block:: java 

   // Define a new map
   Map<String, String> m = new Map<String, String>(); 
   // Insert a new key-value pair in the map
   m.put('key1', 'element 1');                  
   m.put('key2', 'element 2');          

   // Retrieve a value, given a particular key  
   String value = m.get('key1');               
   //remove the value from the map
   m.remove("key1");

References
==========
`https://docs.oracle.com/javase/tutorial/collections/interfaces/ <http://https://docs.oracle.com/javase/tutorial/collections/interfaces/>`_

`https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_methods_system_list.htm <http://>`_

`https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_methods_system_set.htm <http://>`_

`https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_methods_system_map.htm <http://>`_


Summary
=======
This article illustrates the basic difference between the Java and Apex collections.

