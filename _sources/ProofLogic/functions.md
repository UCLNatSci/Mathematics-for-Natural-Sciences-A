# Functions

We are probably quite used to thinking about functions when we plot graphs, such as $y = x^2$ or $y = \cos(x)$, as we idealise in {numref}`FunctionMachine`.

```{figure} ../figures/functionmachine2.png
---
name: FunctionMachine
---
These are examples of a much richer mathematical structure, known as <b>Functions</b>, which we can roughly think of as a machine with inputs and outputs.
```

### Definition of a Function
 To set this up in a firmer mathematical way, we can think about functions as the mapping of elements between different sets.  Lets denote the set 
 $A$, which contain the elements we wish to map unique to elements in another set $B$, this mapping will be the function $f$ from $A$ to $B$:

```{math}
f:\,A \rightarrow B
```
which we read as "$f$ is a function from $A$ to $B$".  The elements of the set $A$, which we think of as the range of values in the inputs, is known as the 
<b>Domain</b> of the function and elements of the set $B$, which we think of as the range of values of the outputs are known as the <b>Target Set</b> or <b>Co-Domain</b> of 
the function.  
 
There are several notations for functions:
|Notation | Meaning |
|---|---|
|$f(x) = x^2$ | $x$ as a variable for the function $f$ |
|   $x \mapsto x^2$ | $x$ goes into $x^2$ |
|    $y = x^2$ | $x$ is the independent variable and & $y$ is the dependent variable |
 
Given a function $f:\, A \rightarrow B$, then for an element $a \in A$ the function $f(a)$ maps $a$ to a unique element in $b \in B$.
 
We call $f(a)$ the <b>Image</b> of $a$ under $f$, or $d(a)$ is the <b>Value</b> of $f$ at $a$ or that $f$ <b>Sends</b> or <b>Maps</b> $a$ into $f(a)$. 
 
The set of all image values is called the <b>Range</b> or <b>Image</b> of $f$, which is denoted as:
```{math}
 \text{Im}(f) = \text{Ran}(f) = f(A) = \{b \in B\,:\, \text{there exists }\, a \in A \,\,\text{for which }\, f(a) = b\}
```
and we should make clear that $\text{Im}(f) \subset B$.
 
Given $f: A \rightarrow B$, then for some subset $A' \subset A$. $f(A')$ denotes the set of images of elements in $A'$ and if $B' \subset B$ and $f^{-1}(B')$ 
denotes the set of elements of A each whose image belongs to $B'$:
```{math}
 f(A') = \{f(a)\,:\,a \in A\} \Longleftrightarrow f^{-1}(B') = \{a\in A\,:\,f(a)\in B\}
```
given we call $f(A')$ the imagine of $A'$, we call $f^{-1}(B')$ the <b>Inverse Image</b> or <b>Preimage</b> of $B'$.

We also define an <b>Identity</b> function $I_A$, which simply send an element back to itself, $I_A:\,A \rightarrow A$:
```{math}
I_A(a) = a
```
for every element $a \in A$.

Finally we can define the <b>Graph</b> of a function $f:\,A \rightarrow B$ as the series of order pairs of elements $a \in A$ mapped to elements $b = f(a) \in B$:
```{math}
\text{Graph of }\,f = \{(a,\,b)\,:\, a \in A,\,b = f(a)\}
```

A function $f$ is defined from a set $A = \{a,\,b,\,c,\,d\}$ into a set $B = \{r,\,s,\,t,\,u\}$. with a mapping:
```{math}
f(a) &= s \\
f(b) &= u \\
f(c) &= r \\
f(d) &= s
```
which we can represent graphically as shown in {numref}`FunctionImage`.
```{figure} ../figures/FunctionImage.png
---
name: FunctionImage
---
The image $f$ is the set $\text{Im}(f) = \{r,\,s,\,u\}$ and the element is $t \notin \text{Im}(f)$ because $t$ is not the image of any 
element of $A$ under $f$ - therefore any elements not mapped <em>to</em> under a function are excluded from the image of the function.
```

The graph of $f$ is the following set of ordered pairs:

```{math}
\{ (a,\,s),\,(b,\,u),\,(c,\,r),\,(d,s) \}
```

## Composite Functions
Using the idea of mapping from one set to another, it is possible to introduce functions of functions or <b>composite functions</b>, mapping from one set to another, through 
some intermediate set.  Consider functions $f:\,A \rightarrow B$ and $g:\,B \rightarrow C$, where the target set $B$ of $f$ is the domain of $g$.  We can call this new function 
the <b>Composition</b> of $f$ and $g$, denoted by:
```{math}
g \circ f \equiv g(f(a)
```
where we emphasise that the composition of functions is read from right to left (and not left to right as we usually do).  We picture this in {numref}`compositefunction`.
```{figure} ../figures/compositefunction.png
---
name: compositefunction
---
We can introduce more and more functions and same rules apply, however we can also consider the associativity of the composition of functions, given 
$f:\,A \rightarrow B,\,g:\, b \rightarrow C,\,h:\,c \rightarrow D$.
```
The composition law is also associative:
```{math}
h \circ(g \circ f) = (h \circ g) \circ f
```
which we prove diagrammatically in {numref}`assocompfns`.

```{figure} ../figures/associativitycompositefunctions.png
---
name: assocompfns
---
Associativity of composite functions.
```

Lets think about two simple functions:
```{math}
f(x) &= x^2\\
g(x) &= \cos(x)
```
We can composite these functions by writing:
```{math}
f(g(x)) &= (f \circ g)(x) &= (\cos(x))^2 \\
g(f(x)) &= (g \circ f)(x) &= \cos(x^2)
```
where we notice that in general $f(g(x)) \neq g(f(x))$.  These composite functions can be built up by looking at the function on the <em>furthest right</em> and 
then adding more functions on to the <em>left hand side</em>.  Suppose we introduce a third function:
```{math}
h(x) = \frac{2}{x}
```
then the six different functional compositions would be:
```{math}
f \circ (g \circ h) &= \left( \cos \left( \frac{2}{x} \right) \right)^2 & f \circ (h \circ g) = \left( \frac{2}{\cos(x)} \right)^2 \\ 
g \circ (h \circ f) &= \cos \left( \frac{2}{x^2} \right) & g \circ (f \circ h) = \cos \left( \left( \frac{2}{x}\right)^2  \right) \\ 
h \circ (f \circ g) &= \frac{2}{\left( \cos (x) \right)^2 } & h \circ (g \circ f) = \frac{2}{\cos(x^2)}
```
and we see that the associativity of these composites can be shown to be true:
```{math}
 f\circ g &= (\cos(x))^2\\
 g \circ h &= \cos\left(\frac{2}{x}\right) \\ 
f \circ (g \circ h) &= (f \circ g) \circ h = \left( \cos \left( \frac{2}{x} \right) \right)^2
```

## Invertibility of Functions
A function $f:\,A \rightarrow B$ is said to be <b>one-to-one</b> or <b>Injective</b>  if different elements in the domain $A$ have distinct images, i.e.
```{math}
f\,\text{ is one-to-one if }\,f(a) = f(a') \Rightarrow a = a'
```
Likewise we can set up a function $f:\,A \rightarrow B$ is said to be an <b>onto</b> function or <b>Surjective</b> if every element $b \in B$ is the image 
of some element $a \in A$, i.e. the image of $f$ is the <em>entire</em> target set $B$:
```{math}
f\,\text{ maps }\,A \text{ onto }\,B\,\text{ if }\,\forall\, b \in B,\, \exists \,a \in A, \,\text{ s.t.}\, f(a) = b
```
A function $f:\,A \rightarrow B$ is said to be <b>invertible</b> if there exists a function $f^{-1}:\, B\rightarrow A$ such that:
```{math}
f^{-1} \circ f = I_A \Longleftrightarrow f \circ f^{-1} = I_B
```
A function $f:\,A \rightarrow B$ is invertible iff $f$ is both one-to-one and onto.  We say such functions are a <b>one-to-one correspondence</b> 
between $A$ and $B$.  This is also known as a <b>Bijection</b>.


Lets consider functions $f_1:\,A \rightarrow B$, $f_2:\,B \rightarrow C$, $f_3:\,C \rightarrow D$, $f_4:\,D \rightarrow E$ depicted in {numref}`InvertibilityOfFunctions`
```{figure} ../figures/InvertibilityOfFunctions.png
---
name: InvertibilityOfFunctions
--- Invertibility of four functions which map elements from $A \rightarrow B \rightarrow C \rightarrow D \rightarrow E$.
```

- $f_1:\,A \rightarrow B$ is one-to-one but not onto, since every element in $A$ has a unique image, but element $3 \in B$ does not have any image under $f_1$.
- $f_2:\,B \rightarrow C$ is both one-to-one and onto, i.e. it is a onto-to-one correspondence for all elements in $B$ and $C$ and thus $f^{-1}:\, C \rightarrow B$ exists.
- $f_3:\,C \rightarrow D$ is not one-to-one but is onto since $f_3(r) = f_3(u) = v$, but every element in $D$ has an image under $f_3$. 
- $f_4:\, D \rightarrow E$ is neither one-to-one nor onto, since $f_4(v) = f_4(w) = z$ and there are elements in $E$ which are not images under $f_4$.

    