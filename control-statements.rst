Control Statements
-------------------
IF Statements
==============

Java
^^^^^

**Simple IF Statements**

:code:`if` statement is the most basic of all the control statements. It tells your program to execute a certain section of code only if a particular test evaluates to true. An  :code:`if` statement consists of a boolean expression followed by one or more statements.

The structure of :code:`if` statement in Java is:

.. code-block:: java

    if(boolean-condition){
     
      Statement;
      
     }

**Example**

.. code-block:: java

    int a=2;

    if(a==2){

       System.out.println("a value is 2");

     }

**IF_ELSE Statements**

An :code:`if` statement can be followed by an optional :code:`else` statement, which executes when the boolean expression is :code:`false`.

The structure of :code:`if-else` statement in java is:

.. code-block:: java

    if(boolean-condition){
       Statements-if-true;
     }

    else{
      Statements-if-false;
    }

**Example**

.. code-block:: java

   int age=18;
   if(age>18){
     System.out.println("Congrats you are eligible for the competation");
   }

   else{
     System.out.println("You are not eligible for the cometation");
    }


Apex
^^^^^

**Simple IF Statements**

The conditional statements in Apex work similar to Java.

Structure of :code:`if` statement in Apex is:

.. code-block:: java

   if(boolean-condition){

     Statements;
   }

**Example**

 .. code-block:: java

   Integer a=2;
   if(a==2){
     system.debug('a value is 2');
    }

**IF-ELSE Statements**

Structure of :code:`if-else` statements in Apex is:


.. code-block:: java

   if(boolean-condition){
     statement-if-true;
   }
   
   else{
      statement-if-false;
   }

**Example**

.. code-block:: java

   Integer age=18;
   if(age>18){
     system.debug(congrats! you are eligible for the quiz');
    }
   else{
     system.debug('You are not eligible for the quiz');
   }

Switch Statement
================

Java
^^^^^

A switch statement allows a variable to tested for equality against a list of values. Each value is called a case, and the variable being switched on is checked for each case.

The structure of :code:`switch` statement in Java is:

.. code-block:: java

   switch(expression){
    case constant-expression :
     Statement(s);
    break; 
   case constant-expression :
    Statement(s);
   break;  //you can have any number of case statements.
  default: 
   statements;
 }

**Example**

.. code-block:: java

   class SwitchDemo {

     public static void main(String[] args) {

        int month = 8;

        switch (month) {

            case 1:  System.out.println("January"); break;
            case 2:  System.out.println("February"); break;
            case 3:  System.out.println("March"); break;
            case 4:  System.out.println("April"); break;
            case 5:  System.out.println("May"); break;
            case 6:  System.out.println("June"); break;
            case 7:  System.out.println("July"); break;
            case 8:  System.out.println("August"); break;
            case 9:  System.out.println("September"); break;
            case 10: System.out.println("October"); break;
            case 11: System.out.println("November"); break;
            case 12: System.out.println("December"); break;
            default: System.out.println("Invalid month.");break;
          }
       }
   }


Apex
^^^^^

Apex does not support :code:`switch` case statements.We will use :code:`if .. else if ..` statements for this purpose. However, formula fields support case syntax, but it eventually compiles into an :code:`if ... else if` format.


The While and Do-While Statements
==================================

Java
^^^^^
**While Loop**

While loop executes a *statement* repeatedly, until the value of *condition* becomes *false*. The test takes place before each iteration.

The structure of :code:`While` loop in Java is:

.. code-block:: java
   
   while(Expression){
      Statement(s);
   }

The :code:`While` statement evaluate *expression*, which must return a *boolean* value. If the expression evaluate *true*,the :code:`While` statement executes the statements in :code:`While` block. The :code:`While` statement continuous testing the expression and executing its block until the expression evaluates to *false*. 

**Example**

.. code-block:: java

   class WhileLoopExample{
        
     public static void main(string[] args){
       int i=10;
       while(i>1){
        System.out.println(i);
        }

     }

  }

**Do-While Loop**

Unlike :code:`For` and :code:`While` loops, which test the loop condition at the top of the loop, the :code:`Do..While` loop checks the condition at the bottom of the loop. 

A :code:`Do..While` loop is similar to the :code:`While` loop, except that a :code:`Do..While` loop is guaranteed to execute at least one time.

The structure of :code:`Do-While` loop in Java is:

.. code-block:: java

   do{
       Statement(s);
   }while(Expression);
   
**Example**
 .. code-block:: java

   public class DoWhileLoopExp{
    
     public static void main(string[] args){

       int count=1;
        do{
           System.out.println("The count is:"  + count);
           count++;
        } while(count<11);

     }   
  
   }

Apex
^^^^^

**while loop**

The :code:`While` and :code:`Do-While` loops works in Apex similar to Java.

The structure of :code:`While` loop in Apex is:

.. code-block:: java
   
   while(condition){
   Code_block;
 
   }

**Example**

.. code-block:: java
   
   Integer count=1;
   while(count<11){
    system.debug(count);
    count++;
  
    }


**Do-While Loop**

The structure of :code:`Do..While` loop in Apex is :

.. code-block:: java

    do{
     code_block;

    }while(condition);
    
**Example**

.. code-block:: java

   Integer count=1;
   do{
     system.debug(count);
     count++;
     } while(count<11);


For loop   
=========

Java
^^^^^

A :code:`For` loop is a repetition control structure that allow you to efficiently write a loop that needs to execute a specific number of times.

The *structure* of a :code:`For` loop in Java is:

.. code-block:: java
  
   for(Initialization; exit_condition; Increment_stmt){
       code_block;
   }

**Example** 

.. code-block:: java
  
   public class ForExp{
     public static void main(string [] args){
      for(int i=1; i<11; i++){
        System.out.println("count is:"+i);
        
       }
    
     }

    }
  
  
**For-each loop**

:code:`for-each` loop is used to access each successive value in a collection of values.It's commonly used to iterate over an array or collection.

The *structure* of :code:`Foe-each` loop in Java is:

.. code-block:: java

    for(declaration : expression){
      statements;
    }
   
**Example**

.. code-block:: java

   public class Udemy {

     public static void main(String args[]){
       int [] numericals = {100, 200, 300, 400, 500};

       for(int u : numericals){
         System.out.print( u );
         System.out.print(",");
        }
        System.out.print("\n");
        String [] titles ={"William", "Beatrice", "Lucy", "Sam"};
        for( String name : titles ) {
        System.out.print( titles );
        System.out.print(",");
        }
      }
    }


Apex
^^^^^
Apex support three variations of the :code:`for` loop 

**Traditional for loop** 

*Syntax:*

.. code-block:: java
   
   for(Init_stmt; exit_condition; Increment_stmt){
    code_block;
  
 }

**Example**

.. code-block:: java

   for(Integer i=1; i<11; i++)
    {
      system.debug('count is:'+ i);
    }
   
**List or Set iteration for loop**

List or Set :code:`for loop` iterates over all the elements in a List or Set.

*Syntax:*

.. code-block:: java
   
   for(Variable : List/Set){
     code_block;
   }

**Example**

.. code-block:: java

  Integer[] numbers= new Ineger[] {1,2,3,4,5,6,7,8,9,10};
   for(Integer i : numbers){
      system.debug(i);
   }

**The soql for loop**

The soql for loop iterate the over all of the sObject records returned by a soql query.

*Syntax:*

.. code-block:: java

    for(variable : [soql query]){
      block_of_code;
    }
  
**Example**

.. code-block:: java

    // Create a list of account records from a SOQL query
    
     List<Account> accs = [SELECT Id, Name FROM Account WHERE Name = 'Siebel']; 

     // Loop through the list and update the Name field
     
      for(Account a : accs){
          a.Name = 'Oracle';
      }

     // Update the database
     
     update accs;


Branching Statements
====================

Break Statement
^^^^^^^^^^^^^^^^

Java
^^^^^

The :code:`break` statement terminates the loop (For,while and Do..While) and Switch statement immediately when it appears.

The *structure* of the :code:`break` statement in Java is:

.. code-block:: java

    break;

**Example**

.. code-block:: java

    // Using break to exit a loop.
    
     class BreakLoop { 
      public static void main(String args[]) { 
        for(int i=0; i<100; i++) { 
         // terminate loop if i is 10 
         if(i == 10) break; 
            System.out.println("i: " + i); 
         } 
          System.out.println("Loop complete."); 
        } 
      }

Apex
^^^^^
The :code:`break` statement in Apex works similar to Java.

**Example**

.. code-block:: java

    for(Integer i=0; i<100; i++) {
      if(i==10)
       break;
      system.debug('i value:' + i);
      }
    





