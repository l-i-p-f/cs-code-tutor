<p><strong>Introduction &amp; Instructions</strong></p>
<p>• In this document are descriptions of three Python miniprojects. Choose one to complete.</p>
<p>• Each of the titles has its own template on Minerva.  Download and use this template, changing the title xxyyzz to your userid. Do not change the given names of functions.</p>
<p>• Each of the three titles will have their own submission link on Minerva.  Make sure you submit your solution to the correct link by <strong>2pm</strong><strong> </strong><strong>on</strong><strong> </strong><strong>Friday</strong><strong> 13th</strong><strong> </strong><strong>December</strong>.</p>
<p>• Your solution should consist of one single Python file, which should generate any graphs, etc., when run. (Do not try to submit text or graphic files separately.)</p>
<p>• Make sure that your file runs, and takes at most 10 seconds to finish.  (If you want to perform longer experiments, you can include this code and discussion of your findings within comments.)</p>
<p>• You should include discussion and commentary as comments within your file (not within print statements).</p>
<p>• Each miniproject consists of three parts.  Each part is worth one third of the total avail- able marks.  (This should give you guidance as to how much work is expected in Part 3.)</p>
<p>• In each case, Part 3 is much more open-ended than the other two parts, and is your chance to demonstrate independent initiative and creativity.</p>
<p>• Make sure that you explain what experiments you have done and what your findings are, as comments within your file.  Creativity, mathematical understanding, and clarity of communication will contribute to your mark as well as coding proficiency.</p>
<p>• You may want to include functions that you have written earlier in the course.  If so, please include them within your .py file (that is, don’t import them from some other file, because we won’t have that file!).  Feel free to import standard libraries that we’ve used, such as math, time, etc..</p>
<p>• During your investigation in these projects, you might investigate the topics online. This is fine. You are advised not to use code written by other people, as this will count against you for individual creativity and initiative.  However, if you do take a section of code from a source online, it is <u>essential</u> that you reference this, by giving the web address in a comment in your file.  Failure  to  declare  code  written by other people will be considered plagiarism.</p>
<p>Option 1:  Sparse Rulers</p>
<p align="justify">An ordinary ruler is a straight piece of wood where distances 0, 1, 2 . . . , N are marked, for some N ≥ 1.  A sparse ruler  (or simply a ruler) is an ordinary ruler from which some of the numbers 1, . . . , N −1 may have been deleted.  The number of marks on the ruler is its order and the value N is its reach.  Here, we will represent a ruler as a Python list of strictly increasing integers starting with 0. For instance  [0,1,3,7] is a ruler of order 4 and reach 7.</p>
<p><strong>Part</strong><strong> </strong><strong>1.</strong></p>
<p>(a) Write functions reach(myruler) and order(myruler) which take as input a list represent- ing a sparse ruler and return its reach and order, respectively.</p>
<p>(b) Write a function isitaruler(mylist) which takes as input a Python list, and returns True if the list represents a ruler (that is to say:  every entry is an integer, the list starts with 0, and each subsequent entry is strictly greater than the previous one), and False otherwise.</p>
<p align="justify">Hint:    Set a variable called oksofar  &#61;&#61;  True which you can set to False if you find a problem. First test whether the list’s initial entry equals 0.  Then loop through the remain- ing entries testing whether they are integers with each strictly greater than the previous.</p>
<p>(c) Write a function sparsenkrulers(n,k) which takes as inputs positive integers n,k where n &#43; 1 ≥ k ≥ 2 and returns a list of all sparse rulers of reach n and order k.</p>
<p>Hint:   the itertools library has a function combinations.  After importing it, the com- mand combinations(mylist,r) will generate all sublists of length r from mylist.</p>
<p align="justify">Start with listofrulers  &#61;  [].  Note that each ruler must contain the entries 0 and n with k-2 others.  Using the technique above, set up a loop through all combinations of k-2 numbers from range(1,n). At each stage, create a ruler which contains the entries 0 and n along with the current combination, sorted into ascending order.  Append it to the listofrulers. After the loop has completed, return listofrulers.</p>
<p align="justify">A sparse ruler of reach N is complete if it is possible to measure all distances between 1 and N by taking the differences between two marks.  For instance  [0,1,3] is complete because the pairs (0, 1), (1, 3), and (0, 3) yield distances of 1, 2, and 3 respectively.  (Note that the pair of marks do not need to be consecutive.) On the other hand,  [0,1,4] is not complete as there is no way to measure a distance of 2.</p>
<p>(d) Write a function ismyrulercomplete(myruler) which takes as input a list representing a sparse ruler of reach N and returns True if it is complete and False otherwise.</p>
<p align="justify">Hint:   Create a list of all differences between entries in the ruler.  The loop through the values 1, . . . ,N testing whether they are in the list of differences.  (Remember, the line of code k  in  mylist will return True or False.)</p>
<p align="justify"><strong>Part  2. </strong>A  Golomb  ruler  is  a  sparse  ruler,  where  the  pairs  of  marks  all  measure different distances. For instance,  [0,1,4] is Golomb as the measurable distances are all distinct:  1,3,4. However  [0,1,2] is not Golomb as the pairs (0, 1) and (1, 2) measure the same distance.</p>
<p>(a) Write a function ismyrulergolomb(myruler) which takes as input a list representing a sparse ruler of reach N and returns True if it is Golomb and False otherwise.</p>
<p>Hint:   Loop through the ruler’s list of differences, and count how many times each occurs. (The code mylist. count(k) will return the number of times k appears in mylist.)</p>
<p>(b) Using the functions you have written, write functions listofgolombrulers(n) which out- puts a list of all Golomb rulers of reach n, and listofcompleterulers(n) which outputs a list of all complete rulers of reach n.</p>
<p>Run your functions on some different values of n and comment on your findings.</p>
<p>The Erd˝os-Tur´an construction produces a sparse ruler of order m &gt; 2 with marks at the points 2mk &#43; (k2  mod m) for each k ∈ 0, . . . , m − 1.</p>
<p>(c) Write a function ErdosTuran(m) which takes as input an integer m &gt; 2 and outputs the corresponding ruler.  Run it on a variety of entries, and comment on the type of rulers that are produced by different inputs.</p>
<p align="justify"><strong>Part</strong><strong> </strong><strong>3. </strong>Continue your investigations into sparse, Golomb, and/or complete rulers. You could consider, for instance, the notion of an optimal Golomb ruler of order k, which is a Golomb ruler of minimal possible reach n.  (That is, that there is no Golomb ruler of order k and reach &lt; n.) Finding these is notoriously difficult as k grows, so do not be too ambitious with the size of k. You could count rulers of different kinds, and plot suitable graphs, commenting on what these tell you.</p>
<p align="justify">Option 2:  Pythagorean Triples &amp; Euler Bricks</p>
<p><strong>Part</strong><strong> </strong><strong>1.</strong></p>
<p align="justify"><strong>Definition</strong><strong>.</strong><strong> </strong>A Pythagorean triple (x,y, z) is a triple of positive integers where x2 &#43; y2  &#61; z2 . This can be thought of as describing an x × y rectangle with the property that the diagonal z is also of integer length.</p>
<p>A Pythagorean triple (x,y, z) is primitive if x,y,z are coprime (i.e. there is no integer k &gt; 1 which divides all of them) .</p>
<p>(a) Write a Python function PrimPyth(n) which returns a list of primitive Pythagorean triples (x,y, z) where 0 &lt; x &lt; y &lt; z &lt; n. For example, PrimPyth(6) should return [(3,4,5)]</p>
<p><strong>Hint</strong><strong>: </strong>In this project we represent triples as tuples  (x,y,z)  not as lists  [x,y,z].  The two data-types behave similarly in many ways.  Do not write a triply nested loop which searches through all triples (x,y, z) as this will take n3  steps!  Instead, use&amp;nbs MATH2920 WEEK 10 MINI-PROJECTS, 2024/25Python p;the fact (proved by Euclid) that every primitive Pythagorean triple arises as (m2  − n2 , 2mn,m2  &#43; n2 ) where m,n are co- prime integers which are not both odd.</p>
<p>(b) Run your function from part (a) with n &#61; 10000 and plot a scattergraph of y against x.</p>
<p>(c) Write a function Pyth(n) which returns a list of (not necessarily primitive) Pythagorean triples (x,y, z) where z &lt; n.</p>
<p><strong>Hint</strong><strong>:</strong><strong> </strong>Use your function from part (a).</p>
<p>(d) Run your function from part (c) with n &#61; 10000 and plot a scattergraph of x against y. (This should be a new figure not overwriting the one from part (b)).</p>
<p>(e) Comment on your the features of your two graphs, writing your answer as a comment.</p>
<p><strong>Part</strong><strong> </strong><strong>2.</strong><strong> </strong>An Euler Brick is an a × b × c cuboid where the dimensions a,b,c are positive integers, as are the diagonals of each face. The first, (44, 117, 240), was discovered in 1719 by Paul Halcke.</p>
<p align="justify">(a) Write a function IsItEuler(triple1,triple2) which accepts as input two tuples repre- senting distinct Pythagorean triples and returns True if together they describe two faces of an Euler Brick, and False otherwise.  For example the inputs (44,117,125),(117,240,267) should return True, as should (117,240,267),(117,44,125), etc..</p>
<p>(b) Write a function Bricks(n) to return a list of Euler bricks (a,b,c) where 0 &lt; a &lt; b &lt; c &lt; n. <strong>Hint:</strong><strong> </strong>Use your functions Pyth and IsItEuler.</p>
<p>(c) How many Euler bricks are there with all dimensions  &lt; 1000? How many of them are primitive? Write your answer as a comment, explaining what a “primitive” Euler brick is.</p>
<p><strong>Part</strong><strong> </strong><strong>3. </strong>Continue your investigations into Pythagorean triples and/or Euler Bricks.  Possible topics include:</p>
<p>• Connections between Fibonacci numbers and Pythagorean triples.  The number 5 is both a Pythagorean hypoteneuse and Fibonacci number. Do other numbers share these properties?</p>
<p>• Pythagorean quadruples (x,y,z, w) where x2  &#43; y2 &#43; z2  &#61; w2 .</p>
<p align="right">• Let x &#43; y &#43; z be the perimeter of the triple (x,y, z).  In 1900, Derrick Lehmer proved that if</p>
<p align="right">N(p) is the number of primitive Pythagorean triples of perimeter ≤ p, then p/N(p) → π2/log2 as p → ∞ .</p>
<p>Option 3:  Approximations of π</p>
<p align="justify">The number π, which can be defined as the ratio of the circumference of a circle to its diameter, is irrational (it cannot be expressed as a fraction, and its decimal representation does not end in a repeating pattern).  This mini-project explores various methods for approximating its value.  First we note that, in floating point arithmetic, the value of π  can be found using the pi constant from the module math:</p>
<p>In[1]  import math</p>
<p>In[2] print(math. pi)</p>
<p>Out[3]:  3 . 141592653589793</p>
<p><strong>Part</strong><strong> </strong><strong>1.</strong></p>
<p>(a) The Gregory-Leibniz formula for π dates from the 1670s (but was apparently known to Indian mathematician Madhava of Sangamagrama around 1400), and states that</p>
<p></p>
<p align="justify">Write a function pi<u> </u>gl(n) which takes as an input an integer n and returns an approxima- tion of π, by evaluating the Gregory-Leibniz formula with n terms.  (For n&#61;5 your function should return 3.3396825396... . Don’t forget to multiply the sum of the series by 4.)</p>
<p>(b) Another series expression for π,  less well-known and discovered by Nikalantha  (around 1500), is</p>
<p></p>
<p align="justify">Write a function pi<u> </u>nik(n) which takes as an input an integer n and returns an approxi- mation of π, by evaluating this formula with n terms.  (For n&#61;3 your function should return 3.1333333... .)</p>
<p>(c) A third expression is due to Wallis (1656):</p>
<p></p>
<p align="justify">Write a function pi<u> </u>wallis(n) which takes an integer n as input and returns an approxi- mation of π by evaluating the Wallis formlua with n brackets in the formula.  (For example, pi<u> </u>wallis(3) should return 2.9257142857... .)</p>
<p>(d) For  the  Gregory-Leibniz  expression,  compute  the  absolute  value  of  the  error  (that  is, abs(pi<u> </u>gl(n)-math. pi)) for n  &#61;  1 to 500.  Store these errors in a list (say, pi<u> </u>gl<u> </u>error), and repeat this for the other two series,  storing the errors in new lists.   Plot  a  graph with the errors pi<u> </u>gl<u> </u>error, pi<u> </u>nik<u> </u>error pi<u> </u>wallis<u> </u>error on the y-axis, against the range(1,500) on the x-axis.  (You should plot all three lines on the same graph.  Be sure to label axes and data. You should choose for yourself whether plot, loglog or semilogy gives the most meaningful plot.)</p>
<p>(e) Give a brief comment on the rate at which each expression converges to π .</p>
<p><strong>Part</strong><strong> </strong><strong>2. </strong>Euler gave two remarkable expressions for π, which involve prime numbers, and in the</p>
<p>second case, also prime factorisations of composites.</p>
<p>(a) The following is an infinite product expression:</p>
<p></p>
<p align="justify">In this formula, the numerators are the primes &gt; 2, while each denominator is the multiple of 4 closest to the numerator. Write a function pi<u> </u>euler1(n) which computes the value of the first n terms in the product.  For example, pi<u> </u>euler1(3) should return 3.28125.</p>
<p>(b) The next formula is an infinite sum:</p>
<p></p>
<p align="justify">In this formula, each fraction 1/n has a sign (±) determined by: the first two terms have positive signs; after that, if the denominator is a prime of the form 4m − 1 (for example, n &#61; 3, 7, 11, . . .), the sign is positive; if the denominator is a prime of the form 4m &#43; 1 (for example, n &#61; 5, 13, 17, . . .), the sign is negative; if the denominator is a composite number, then the sign is equal to the product of the signs corresponding to its factors (for example, n &#61; 9 &#61; 3 × 3, so its sign is positive (a positive times a positive), while n &#61; 10 &#61; 5 × 2, so its sign is negative (a negative times a positive)). Write a function pi<u> </u>euler2(n) which computes the value of the first n terms of this expression.   For example, pi<u> </u>euler2(2) should return 1.5.</p>
<p>(c) Compute the errors for both Euler expressions, as in part 1, again for n&#61;1 to 500.  Plot a graph showing the errors for both Euler expressions, together with the errors for the previous three approximations from part 1, on the same graph.  Comment briefly on the convergence of the Euler methods.</p>
<p>(d) Recall the Monte Carlo method, from week 6 (section 6.2.2), for approximating π .  Suppose we choose a point  (x,y) randomly  (with uniform distribution) in the unit square.   The probability that it lies inside a circle of diameter 1 contained in the unit square is equal to the area of that circle, or π/4.  So this Monte Carlo method works as follows:</p>
<p>(i) Generate a large number M of points (x,y) with both x and y uniformly distributed random variables in [0, 1]. You can use the module random to do this, as this module contains a function (also called random) which returns a number from the uniform distribution on [0, 1].</p>
<p>(ii) For each (x,y) produced, check whether it lies inside a circle of diameter 1 centred at</p>
<p>(0.5, 0.5). Let the number of such points be Min.    (iii) Then an approximation for π is given by 4Min /M.</p>
<p align="justify">Write a function montecarlo(M) which takes an integer M and returns an approximation to π .  (I can’t give you an example output, as the random nature of the procedure means approximations will differ!)</p>
<p>(e) Write a function montecarlo<u> </u>accuracy(eps) which takes as an input some small float eps, and repeatedly performs the Monte Carlo procedure, until the approximation has an error </p>
<p><strong>Part</strong><strong> </strong><strong>3. </strong>Continue your investigation. The following are all suggestions, not requirements, and you certainly shouldn’t attempt to investigate all of these. You might investigate:</p>
<p>• more quickly convergent methods, like the Gauss-Legendre algorithm, the Borwein al- gorithm, or others.</p>
<p>• approximations given by the continued fraction expansion for π .</p>
<p>• digit extraction methods.</p>
<p>• the decimal module, for obtaining more accuracy than floating point arithmetic allows         </p>