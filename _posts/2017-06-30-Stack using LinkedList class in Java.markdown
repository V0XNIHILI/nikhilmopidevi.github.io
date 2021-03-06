---
layout: post
title:  "Stack using LinkedList class in Java"
date:   2017-06-30 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Stack, Linked List, LinkedList, LinkedList class, Deque]
comments: true
---

Stack is a linear data structure which follows the Last-In-First-Out (LIFO) approach, where the last element inserted is the first one to be removed.

In this post, we'll see how to implement a stack using the **LinkedList** class. Java provides the **LinkedList** class as part of the Java Collections Framework. For an overview of the Java Collections Framework, check out my post [Overview of the Java Collections Framework]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}){:target="_blank"}.

Some important methods provided by the **LinkedList** class are:
1. push(E element)
2. pop()
3. peek()
4. isEmpty()

**LinkedList** class permits all elements, including `null`. But it is not recommended to insert nulls because `null` is used as a special return value by various methods to indicate that the deque is empty.

The following example demonstrates how to implement a stack using the **LinkedList** class.

## Example

{% highlight java %}
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {

        //Creates a stack of integers
        LinkedList<Integer> stack = new LinkedList<Integer>();

        //Pushes some integers into the stack
        stack.push(2);
        stack.push(5);
        stack.push(6);

        //Peeks into the stack
        System.out.println("Current element at the top of the stack: " + stack.peek());

        //Pops one integer from the stack
        System.out.println("Element popped from the stack: " + stack.pop());

        //Iterates through the stack
        System.out.print("Current elements in the stack: ");
        while(!stack.isEmpty()) {
            System.out.print(stack.pop() + " ");
        }

    }
}
{% endhighlight %}

## Output

{% highlight java %}
Current element at the top of the stack: 6
Element popped from the stack: 6
Current elements in the stack: 5 2 
{% endhighlight %}

Let us look closely at each method used in the above program.

## Methods 

#### **1) push(E element)**
This method pushes an element onto the stack represented by this list. In other words, it inserts the element at the front of this list.

Consider a stack with the following elements from top: **"Banana"** **"Apple"** 
{% highlight java %}
stack.push("Orange");
{% endhighlight %}

This method pushes the string **"Orange"** to the top of the stack. Now, the elements in the stack are: **"Orange"** **"Banana"** **"Apple"**

#### **2) pop()**
This method pops an element from the stack represented by this list. In other words, it removes and returns the first element of this list.

If the stack is empty, a `‘NoSuchElementException’` exception is thrown.

{% highlight java %}
String fruit = stack.pop(); //stores the returned string in the variable 'fruit'
{% endhighlight %}

This method removes and returns the string **"Orange"** which is at the top of the stack.

#### **3) peek()**
It retrieves, but does not remove, the head (first element) of this list. As the name indicates, it is similar to peeking at the top of the stack.

{% highlight java %}
String fruit = stack.peek(); //stores the returned string in the variable 'fruit'
{% endhighlight %}

This call to the method returns the string **"Banana"** which is at the top of the stack, but doesn't remove it from the stack.

#### **4) isEmpty()**
This method tests if the stack is empty. It returns **true** if the stack is empty or **false** otherwise.

{% highlight java %}
//This loop continues to execute till the stack is empty
while(!stack.isEmpty()) {
    //some code
}
{% endhighlight %}

The above `while` loop continues to execute until the stack is empty.

Now since you know how to implement a stack using the **LinkedList** class, check out other ways to create a stack:

* [Stack using ArrayDeque]({{ site.baseurl }}{% post_url 2017-07-02-Stack using ArrayDeque class in Java %}){:target="_blank"}
* [Stack class]({{ site.baseurl }}{% post_url 2017-06-25-Stack class in Java %}){:target="_blank"}

