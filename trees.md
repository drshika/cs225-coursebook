<div>

[CS 225 Spring 2019 :: TA Lecture Notes ]{.c18 .c44}

[2/11  Iterators]{.c44 .c18}

[By Wenjie]{.c18 .c48}

[![](images/image1.png "horizontal line"){style="width: 624.00px; height: 4.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 4.00px;"}

</div>

-   ### [Queue Implementation]{.c39} {#h.7m1v0r5w5ez4 style="display:inline"}

```{=html}
<!-- -->
```
-   [We can ]{.c18}[implement queue]{.c18}[ using an array list.]{.c3}
-   [Adding:]{.c3}

```{=html}
<!-- -->
```
-   [If we add an element to the array in front, we need to copy every
    element one spot up to create space for the new element in front.
    ]{.c3}
-   [Previously we ]{.c18}[said handle]{.c18}[ "add in front"
    efficiently by using smart indexing.]{.c3}
-   [Lastly we need to increment capacity of the queue]{.c3}

```{=html}
<!-- -->
```
-   [When we are out of space:]{.c3}

```{=html}
<!-- -->
```
-   [We can double the array]{.c3}
-   [But be careful how we copy the data over - need to copy data such
    ]{.c18}[that]{.c18}[ ]{.c18}[the start of the queue]{.c18}[ is at
    the index = 0]{.c18}[.]{.c3}

[]{.c3}

[                          Full Q]{.c3}

[]{#t.7dfa0236fb66f3194ee296508a004cba03a041c3}[]{#t.0}

  ---------- ---------- ---------- ----------
  [a]{.c3}   [y]{.c3}   [i]{.c3}   [s]{.c3}
  ---------- ---------- ---------- ----------

[                                                            ↑]{.c18}

[                                                                     
 start]{.c3}

[Incorrect]{.c3}

[]{#t.081f78df967a4d2a421c095225924910a69fc9e2}[]{#t.1}

  ---------- ---------- ---------- ---------- --------- --------- --------- ---------
  [a]{.c3}   [y]{.c3}   [i]{.c3}   [s]{.c3}   []{.c3}   []{.c3}   []{.c3}   []{.c3}
  ---------- ---------- ---------- ---------- --------- --------- --------- ---------

[                                  ↑]{.c3}

[                               
Start                                                        ]{.c3}

[Correct]{.c3}

[]{#t.8c9294d8dfc28825db66e9667294c8e59c14536d}[]{#t.2}

  ----------- ----------- ----------- ----------- ---------- ---------- ---------- ----------
  [i]{.c14}   [s]{.c14}   [a]{.c14}   [y]{.c14}   []{.c14}   []{.c14}   []{.c14}   []{.c14}
  ----------- ----------- ----------- ----------- ---------- ---------- ---------- ----------

[        ↑]{.c3}

[   
 Starts                                                                                ]{.c3}

[]{.c3}

[]{.c3}

[Three data storage strategies]{.c14}

-   [When we talked about the functions we said that we can pass/return
    by value, reference, and pointer. The same concept applies to
    storing data]{.c18}[. We can store data by value, reference, and
    pointer. ]{.c3}

[]{.c3}

[]{#t.b6dbeb1f3c9fb99a2aabb2480484d933f00990c1}[]{#t.3}

+-----------------------------------+-----------------------------------+
| [5]{.c3}                          | [T & data; // store by            |
|                                   | reference]{.c3}                   |
| [6]{.c3}                          |                                   |
|                                   | []{.c3}                           |
| [7]{.c3}                          |                                   |
|                                   | [T \* data; // store by           |
| [8]{.c3}                          | pointer]{.c3}                     |
|                                   |                                   |
| [9]{.c3}                          | []{.c3}                           |
|                                   |                                   |
|                                   | [T data; // store by value]{.c3}  |
+-----------------------------------+-----------------------------------+

[]{.c3}

#### [There are tradeoffs among the three:]{.c18 .c43} {#h.k19utv2dl8pp .c31 .c50}

-   [Data life cycle management:]{.c3}

```{=html}
<!-- -->
```
-   [By reference]{.c5}[ - a reference is an alias to a variable,
    therefore storing a reference means that we do not own that data. It
    is somewhere ]{.c18}[on client's]{.c18}[ stack and when the client
    code finishes, the data is going to be deleted. ]{.c3}
-   [By pointer]{.c5}[ - a pointer has its own memory, but similarly to
    the reference it points to a memory space that we do not control.
    The client code owns the memory and when it finishes the memory is
    going to be freed.]{.c3}
-   [By value]{.c5}[ - in this case, we are going to get a copy of the
    object and we are completely in charge of the data. The only time it
    can get deleted is when our code is done or deletes the data. ]{.c3}

```{=html}
<!-- -->
```
-   [Storing NULL as the data:]{.c3}

```{=html}
<!-- -->
```
-   [By reference]{.c5}[ - a reference can never be a null, therefore we
    cannot have NULL stored.]{.c3}
-   [By pointer]{.c5}[ - a pointer can hold NULL value and we can store
    it as data.]{.c3}
-   [By value]{.c5}[ - when we create an object, either a custom
    constructor or a default automatic constructor will be called.
    Therefore, the data will never be NULL.]{.c3}

```{=html}
<!-- -->
```
-   [Effects on stored data when the data is manipulated from user code
    (safety):]{.c3}

```{=html}
<!-- -->
```
-   [By reference]{.c5}[ - our data is an alias to the data in the
    client code, thereby when the client code changes the data, the data
    we store gets changed as well.]{.c3}
-   [By pointer]{.c5}[ - our data points to the memory block that
    belongs to the client code. Therefore, as in the case of the
    reference, if the client code changes the data, the data we store
    gets changed as well.]{.c3}
-   [By value]{.c5}[ - the data we store belongs to us and the changes
    made by the client code do not affect what we have stored.  ]{.c3}

```{=html}
<!-- -->
```
-   [The relative speed of storage methods:]{.c3}

```{=html}
<!-- -->
```
-   [By reference]{.c5}[  - we are only storing an address. We don't
    need more memory and we don't need to use a copy constructor.
    Therefore, this is a fast method.]{.c3}
-   [By pointer]{.c5}[ - as for the reference, we are storing an address
    and this is a fast method.]{.c3}
-   [By value]{.c5}[ - in this case we need more memory to store the
    whole object and we need to use a copy constructor. Therefore,
    storing the data by value is slow. ]{.c3}

[]{.c3}

-   ### [Iterators]{.c39} {#h.xdlz8vw5nofy style="display:inline"}

-   [Definition: Iterators are used to read the data from different data
    structures in a uniform way (a common interface). In other words,
    iterators maintain a list of data for client code. They are used to
    keep track of where we are, what is next, and what is the data in
    the data structure.]{.c3}

-   [Implementation: ]{.c3}

```{=html}
<!-- -->
```
-   [In the implementing class]{.c3}

```{=html}
<!-- -->
```
-   [::begin(); ]{.c16}[return an iterator that is at the beginning of
    the data]{.c3}
-   [::end(); ]{.c16}[return an iterator ]{.c18}[one past ]{.c15}[the
    last data]{.c3}

```{=html}
<!-- -->
```
-   [In the iterator class]{.c3}

```{=html}
<!-- -->
```
-   [base class: ]{.c18}[std::iterator]{.c8}
-   [it requires us to implement basic functionality:]{.c3}

```{=html}
<!-- -->
```
-   [operator++;]{.c16}[   move to the next]{.c3}
-   [operator\*;  ]{.c16}[ dereferencing operator: returns data]{.c3}
-   [operator!=; ]{.c16}[ not equal operator: to check the end]{.c3}

```{=html}
<!-- -->
```
-   [Using an iterator]{.c3}

[]{#t.7ba170449a41649d5d861d453344b29926badb32}[]{#t.4}

+-----------------------------------+-----------------------------------+
| [stlList.cpp]{.c45}               |                                   |
+-----------------------------------+-----------------------------------+
| [1]{.c7}                          | [#include \<list\>]{.c8}          |
|                                   |                                   |
| [2]{.c7}                          | [#include \<string\>]{.c8}        |
|                                   |                                   |
| [3]{.c7}                          | [#include \<iostream\>]{.c8}      |
|                                   |                                   |
| [4]{.c7}                          | [struct Animal { ]{.c16}[//       |
|                                   | struct is a class with all        |
| [5]{.c7}                          | members public]{.c11}             |
|                                   |                                   |
| [6]{.c7}                          | [  std::string name, food;]{.c8}  |
|                                   |                                   |
| [7]{.c7}                          | [  bool big;]{.c8}                |
|                                   |                                   |
| [8]{.c7}                          | [  Animal(std::string name =      |
|                                   | \"blob\", std::string food =      |
| [9]{.c7}                          | \"you\", bool big = true)]{.c8}   |
|                                   |                                   |
| [10]{.c7}                         | [    : name(name), food(food),    |
|                                   | big(big) {};]{.c8}                |
| [11]{.c7}                         |                                   |
|                                   | [    ]{.c16}[// constructor with  |
| [12]{.c7}                         | default values]{.c11}             |
|                                   |                                   |
| [13]{.c7}                         | [    // this implicitly defines a |
|                                   | default constructor]{.c11}        |
| [14]{.c7}                         |                                   |
|                                   | [  int main() {]{.c8}             |
| [15]{.c7}                         |                                   |
|                                   | [    Animal g(\"giraffe\",        |
| [16]{.c7}                         | \"leaves\", true), p(\"penguin\", |
|                                   | \"fish\", false), b(\"bear\");    |
| [17]{.c7}                         |  ]{.c16}[//same as b("bear",      |
|                                   | "you", true);]{.c11}              |
| [18]{.c7}                         |                                   |
|                                   | [    ]{.c8}                       |
| [19]{.c7}                         |                                   |
|                                   | [    std::vector zoo;]{.c8}       |
| [20]{.c7}                         |                                   |
|                                   | [    zoo.push_back(g);]{.c8}      |
| [21]{.c7}                         |                                   |
|                                   | [    zoo.push_back(p);            |
| [22]{.c7}                         |  ]{.c16}[// std::vector's         |
|                                   | insertAtEnd]{.c11}                |
| [23]{.c7}                         |                                   |
|                                   | [    zoo.push_back(b);]{.c8}      |
| [24]{.c7}                         |                                   |
|                                   | []{.c8}                           |
| [25]{.c7}                         |                                   |
|                                   | [    for                          |
| [26]{.c7}                         | (std::vector\<Animal\>::iterator  |
|                                   | it = zoo.begin(); it !=           |
| [27]{.c7}                         | zoo.end(); it++) {]{.c8}          |
|                                   |                                   |
| [28]{.c7}                         | [      std::cout \<\< (\*it).name |
|                                   | \<\< \" \" \<\< (\*it).food \<\<  |
| [29]{.c7}                         | std::endl;]{.c8}                  |
|                                   |                                   |
| [30]{.c7}                         | [    }]{.c8}                      |
|                                   |                                   |
| [31]{.c7}                         | []{.c8}                           |
|                                   |                                   |
| [32]{.c7}                         | [/\*]{.c16}                       |
|                                   |                                   |
| [33]{.c7}                         | [    ]{.c16}[// instead, we can   |
|                                   | use "for each loop"]{.c20 .c36}   |
|                                   |                                   |
|                                   | [    for (const                   |
|                                   | ]{.c16}[Animal]{.c20}[ & animal : |
|                                   | ]{.c16}[zoo]{.c54}[) {]{.c8}      |
|                                   |                                   |
|                                   | [      std::cout \<\< animal.name |
|                                   | \<\< " " \<\< animal.food \<\<    |
|                                   | std::endl;]{.c8}                  |
|                                   |                                   |
|                                   | [    }]{.c8}                      |
|                                   |                                   |
|                                   | [\*/]{.c8}                        |
|                                   |                                   |
|                                   | [    return 0;]{.c8}              |
|                                   |                                   |
|                                   | [}]{.c8}                          |
+-----------------------------------+-----------------------------------+

[]{.c3}

-   [For each loop]{.c3}

```{=html}
<!-- -->
```
-   [Always const: we are not be able to modify the variable]{.c3}
-   [We do not care what the data structure is when using an iterator
    this way]{.c3}

```{=html}
<!-- -->
```
-   [If instead of vector, we use multimap, the for loop will be the
    same]{.c3}

[]{#t.eae2f7731d54859d61139b91f973c2cc0fda14c5}[]{#t.5}

+-----------------------------------+-----------------------------------+
| [1]{.c7}                          | [for ( const                      |
|                                   | ]{.c16}[TYPE]{.c20}[ & variable : |
| [2]{.c7}                          | ]{.c16}[collection]{.c37}[ )      |
|                                   | {]{.c8}                           |
| [3]{.c7}                          |                                   |
|                                   | [  // ...]{.c8}                   |
|                                   |                                   |
|                                   | [}]{.c8}                          |
+-----------------------------------+-----------------------------------+

[]{.c3}

[]{.c7}
