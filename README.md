Download Link: https://assignmentchef.com/product/solved-math567-homework-3
<br>
<ol>

 <li><em>Linear two-point boundary value problems: Finite differences</em>

  <ul>

   <li>Implement a general function in whatever language you like for numerically solving the general two-point boundary value problem (TPBVP)</li>

  </ul></li>

</ol>

<em>u</em><sup>00 </sup>= <em>p</em>(<em>x</em>)<em>u</em><sup>0 </sup>+ <em>q</em>(<em>x</em>)<em>u </em>+ <em>r</em>(<em>x</em>)<em>, x </em>∈ [0<em>,</em>1]<em>, u</em>(0) = <em>α, u</em>(1) = <em>β</em>

using centered, second-order finite differences. Your routine should be called fd2tpbvp, and should be entirely general (i.e. it should take as input functions representing <em>p</em>(<em>x</em>), <em>q</em>(<em>x</em>), &amp; <em>r</em>(<em>x</em>), values for <em>α </em>&amp; <em>β</em>, and the number of interior discretization points <em>m</em>). Send me an electronic copy of the code and include a listing of the code in your write-up.

<ul>

 <li>Use your function from part (a) to numerically approximate the TPBVP</li>

</ul>

<em>u</em><sup>00 </sup>= 2tan(<em>x</em>)<em>u</em><sup>0 </sup>+ 2<em>, u</em>(0) = <em>u</em>(1) = 0<em>,</em>

which has the exact solution <em>u</em>(<em>x</em>) = (<em>x </em>− 1)tan(<em>x</em>). Compare the approximate solution to the exact solution using <em>m </em>= 10<em>,</em>20<em>,</em>40<em>,</em>80<em>,</em>160 equally spaced interior points over [0<em>,</em>1] (i.e. <em>x<sub>j </sub></em>= <em>jh</em>, <em>j </em>= 1<em>,…,m</em>, with <em>h </em>= 1<em>/</em>(<em>m </em>+ 1)) and verify numerically that the approximate solution is second-order accurate.

<ol start="2">

 <li><em>Fictitious point method for Robin boundary conditions. </em>Consider the TPBVP</li>

</ol>

<em>u</em><sup>00 </sup>= <em>p</em>(<em>x</em>)<em>u</em><sup>0 </sup>+ <em>q</em>(<em>x</em>)<em>u </em>+ <em>r</em>(<em>x</em>)<em>, x </em>∈ [<em>a,b</em>]<em>,</em>

with mixed boundary conditions

<em>u</em>(<em>a</em>) = <em>α </em>and <em>β</em><sub>1</sub><em>u</em>(<em>b</em>) + <em>β</em><sub>2</sub><em><sup>u</sup></em><sup>0</sup>(<em>b</em>) = <em>β</em><sub>3</sub><em>.</em>

Suppose we discretize the equation with <em>m</em>+1 equally-spaced subintervals of spacing <em>h</em>. Using the fictitious point method described in in class, derive the following second-order accurate finite difference approximation for <em>u<sub>m</sub></em><sub>+1</sub>:

<em>,</em>

where <em>u</em>(<em>b</em>) ≈ <em>u<sub>m</sub></em><sub>+1</sub>, <em>u</em>(<em>b </em>− <em>h</em>) ≈ <em>u<sub>m</sub></em>, <em>p<sub>m</sub></em><sub>+1 </sub>= <em>p</em>(<em>b</em>), <em>q<sub>m</sub></em><sub>+1 </sub>= <em>q</em>(<em>b</em>), and <em>r<sub>m</sub></em><sub>+1 </sub>= <em>r</em>(<em>b</em>).

<ol start="3">

 <li><em>Neumann-Neumman boundary conditions</em>. Consider the 1D Poisson equation with NeumannNeumann boundary conditions</li>

</ol>

<em>u</em><sup>00</sup>(<em>x</em>) = <em>f</em>(<em>x</em>)<em>, a </em>≤ <em>x </em>≤ <em>b, u</em><sup>0</sup>(<em>a</em>) = <em>σ</em><sub>0</sub><em>, u</em><sup>0</sup>(<em>b</em>) = <em>σ</em><sub>1</sub><em>.                                     </em>(1)

As discussed in class this equation has an infinite number of solutions if

(the so-called compatibility condition), otherwise there is no solution. If <em>σ</em><sub>0 </sub>= <em>σ</em><sub>1 </sub>= 0 (i.e. the zero-flux condition) then it can be shown that solutions to the Poisson equation are unique up to an additive constant. If we discretize this BVP at <em>m </em>+ 2 equally-spaced points across [<em>a,b</em>] and use second-order accurate FD formulas in the interior and the second-order accurate fictitious point method at the boundary, we arrive at the linear system

<strong>b</strong>

where <em>h </em>= (<em>b </em>− <em>a</em>)<em>/</em>(<em>m </em>+ 1), <em>f<sub>j </sub></em>= <em>f</em>(<em>x<sub>j</sub></em>), and <em>x<sub>j </sub></em>= <em>a </em>+ <em>jh</em>, <em>j </em>= 0<em>,…,m </em>+ 1.

As discussed in class (and by simple inspection), the matrix <em>A </em>in this equation is singular since every row sums to zero. This means that the vector of length <em>m </em>+ 2

<strong>e </strong>= [1     1     <em>…     </em>1]<em><sup>T</sup></em>

is an eigenvector corresponding to a zero eigenvalue: <em>A</em><strong>e </strong>= <strong>0</strong>. Furthermore, it is the only eigenvector (up to a non-zero multiplicative constant) with this property, i.e. it is the only vector in the null-space of <em>A</em>. Another property of <em>A </em>is that the vector of length <em>m </em>+ 2

<strong>w </strong>

is an eigenvector of <em>A<sup>T </sup></em>corresponding to a zero eigenvalue: <em>A<sup>T</sup></em><strong>w </strong>= <strong>0 </strong>or <strong>w</strong><em><sup>T</sup>A </em>= <strong>0</strong><em><sup>T</sup></em>. It is also the only eigenvector (up to a non-zero multiplicative constant) with this property, i.e. it is the only vector in the null-space of <em>A<sup>T</sup></em>.

A result from linear algebra (known as the <em>Fredholm Alternative</em>) is that the system <em>A</em><strong>u </strong>= <strong>b </strong>has an infinite number of solutions if <strong>w</strong><em><sup>T</sup></em><strong>b </strong>= 0 (which guarantees <strong>b </strong>is in the column space of <em>A</em>). This condition can be viewed as a discrete version of the continuous compatibility condition.

This is all beautiful theory, but in practice what we want to do is actually compute one of the solutions to the BVP. This homework problem and the next one discuss two approaches (with this problem being the most general of the two) for computing a solution with a “direct” method. It should be noted that effective “iterative” methods can also be used. The overall goal of any of these methods is to make the problem unique by adding on an additional constraint. In the continuous problem, especially for the zero-flux case, this is typically accomplished by specifying the “total amount” of <em>u </em>in the domain, which mathematically we write as

(3)

For the zero-flux case, this fixes the arbitrary constant in the solution to be equal to <em>U</em>. This same approach is followed in the discrete problem as well, with the discrete version of this integral taking the form

where we have used the fact that <em>h </em>= (<em>b </em>− <em>a</em>)<em>/</em>(<em>m </em>+ 1). Note that this is just the Trapezoidal rule approximation to (3).

The discrete problem (2) can now be converted into the following equality-constrained quadratic programming problem:

min <em>J</em>(<strong>u</strong>) = 1<strong>u</strong><em>TA</em><strong>u </strong>− <strong>u</strong><em>T</em><strong>b</strong>

2                                                                          (4)

subject to <strong>w</strong><em><sup>T</sup></em><strong>u </strong>= (<em>m </em>+ 1)<em>U</em>

The method of <em>Lagrange multipliers </em>can be used to solve this problem. The idea is to form the <em>Lagrangian</em>

<em>,</em>

and find where the gradient is zero (in general one looks for the <em>saddle points </em>of L). Here the gradient is defined as

<em> .</em>

Applying this to the Lagrangian gives

∇L(<strong>u</strong><em>,λ</em>) = <em>A</em><strong>u </strong>− <strong>b </strong>+ <em>λ</em><strong>w </strong>= 0<em>,</em>

which is a linear system of <em>m</em>+2 equations and <em>m</em>+3 unknowns, <strong>u </strong>and <em>λ</em>. Using the constraint <strong>w</strong><em><sup>T</sup></em><strong>u </strong>= (<em>m </em>+ 1)<em>U </em>gives one extra equation and leads to the (<em>m </em>+ 3)-by-(<em>m </em>+ 3) linear system of equations

<em> .                                                 </em>(5)

This is an example of a more general type of linear system called a “saddle point system”.

<ul>

 <li>Show that the linear system (5) has a unique solution regardless of <strong>b</strong>.</li>

</ul>

Hint: One way to proceed is to show that the only solution to (i) <em>A</em><strong>u </strong>+ <em>λ</em><strong>w </strong>= <strong>0 </strong>and (ii) <strong>w</strong><em><sup>T</sup></em><strong>u </strong>= 0 (i.e. the system (5) with the right hand side set to zero) is <strong>u </strong>= <strong>0 </strong>and <em>λ </em>= 0. One way to show this is to consider what happens when multiplying the first equation by <strong>w</strong><em><sup>T</sup></em>. This should give you the result that <em>A</em><strong>u </strong>= <strong>0</strong>, which means <strong>u </strong>= <em>α</em><strong>e </strong>for some <em>α</em>. You can then use the equation <strong>w</strong><em><sup>T</sup></em><strong>u </strong>= 0 to show that <em>α </em>= 0.

<ul>

 <li>Show that if <strong>w</strong><em><sup>T</sup></em><strong>b </strong>= 0 in (5) then <em>λ </em>= 0. This means that the solution <strong>u </strong>from (5) solves the original system (2) and thus gives an approximate solution to the BVP (6).</li>

</ul>

Note: If <strong>w</strong><em><sup>T</sup></em><strong>b </strong>6= 0 then the solution <strong>u </strong>from (5) does not solve (2), however, <strong>u </strong>may still approximately solve the BVP (6). This will be reflected in the size of <em>λ</em>, since k<em>A</em><strong>u </strong>− <strong>b</strong>k = |<em>λ</em>|k<strong>w</strong>k. If |<em>λ</em>| = <em>O</em>(<em>h</em><sup>2</sup>) then <strong>u </strong>will solve the BVP up to <em>O</em>(<em>h</em><sup>2</sup>) since this is the truncation error of the FD method.

<ul>

 <li>Solve the BVP (6) numerically with <em>a </em>= 0, <em>b </em>= 2<em>π</em>, <em>m </em>= 99, <em>f</em>(<em>x</em>) = −4cos(2<em>x</em>), and <em>σ</em><sub>0 </sub>= <em>σ</em><sub>1 </sub>= 0 using the augmented linear system (5). Set <em>U </em>= 0 and check your answer against the true solution <em>u</em>(<em>x</em>) = cos(2<em>x</em>). Plot the error in the approximate solution and report the relative two-norm of the error. Also report the value of <em>λ</em>. What does this value tell you about your solution in regards to solving the system (2).</li>

 <li>Repeat part (c) but now for the function <em>f</em>(<em>x</em>) = <em>x</em>, <em>σ</em><sub>0 </sub>= −<em>π</em><sup>2</sup>, and <em>σ</em><sub>1 </sub>= <em>π</em><sup>2</sup>. Plot the numerical solution you obtain and report the value of <em>λ</em>. Does it seem reasonable that this approximately solves (2)? Explain.</li>

</ul>

<ol start="4">

 <li><em>Neumann-Neumman boundary conditions and the Discrete Cosine Transform</em>. Consider again the Neumann-Neumann Poisson equation, but now with strictly zero-flux boundary conditions</li>

</ol>

<em>u</em><sup>00</sup>(<em>x</em>) = <em>f</em>(<em>x</em>)<em>, a </em>≤ <em>x </em>≤ <em>b, u</em><sup>0</sup>(<em>a</em>) = 0<em>, u</em><sup>0</sup>(<em>b</em>) = 0<em>.                                       </em>(6)

In this problem, we will look at different way to solve the corresponding linear system (2) that results from discretizing this problem with a second-order accurate FD formula. Here we again let <em>h </em>= (<em>b </em>− <em>a</em>)<em>/</em>(<em>m </em>+ 1), <em>x<sub>j </sub></em>= <em>a </em>+ <em>jh</em>, <em>u<sub>j </sub></em>≈ <em>u</em>(<em>x<sub>j</sub></em>), and <em>f<sub>j </sub></em>= <em>f</em>(<em>x<sub>j</sub></em>) for <em>j </em>= 0<em>,…,m </em>+ 1. In this approximation, the fictitious point idea has been applied, which used the assumption

and     <em>,            </em>(7)

where <em>u</em><sub>−1 </sub>≈ <em>u</em>(<em>x</em><sub>0 </sub>− <em>h</em>) and <em>u<sub>m</sub></em><sub>+2 </sub>≈ <em>u</em>(<em>x<sub>m</sub></em><sub>+1 </sub>+ <em>h</em>). The method that we will use is based on the Discrete Cosine Transform (DCT).

<ul>

 <li>Consider the vectors <strong>u </strong>and <strong>f </strong>= <strong>b </strong>in (2) of length <em>m</em>+2. Let <strong>u</strong>ˆ and <sup>ˆ</sup><strong>f </strong>denote the DCT of these vectors, respectively, i.e.</li>

</ul>

<em>,</em>

for <em>k </em>= 0<em>,…,m </em>+ 1. Now, we can express the entries of <strong>u </strong>and <strong>b </strong>as

<em>,</em>

Substitute these expressions into the linear system (2) to show that row <em>j </em>of this systems simplifies to

<em> ,</em>

in the case of <em>j </em>= 0 and <em>j </em>= <em>m </em>+ 1 use (7).

<ul>

 <li>Use the results from part (a) to show that the DCT of the solution to (2) for <em>k </em>= 1<em>,…,m </em>+ 1 is given by</li>

</ul>

<em>.</em>

However, for <em>k </em>= 0, the value of ˆ<em>u<sub>k </sub></em>is undefined. For this case, note that if <em>f</em><sup>ˆ</sup><sub>0 </sub>= 0 (or

“numerically zero”) then ˆ<em>u</em><sub>0 </sub>can be chosen arbitrarily. Show how the condition <em>f</em><sup>ˆ</sup><sub>0 </sub>= 0 corresponds to the discrete compatibility condition <strong>w</strong><em><sup>T</sup></em><strong>b </strong>= <strong>w</strong><em><sup>T</sup></em><strong>f </strong>= 0 discussed in the previous problem.

<ul>

 <li>Put parts (a) and (b) together to explain how to obtain the solution to (2) when the right hand satisfies <strong>w</strong><em><sup>T</sup></em><strong>f </strong>= 0. Also explain how one makes the solution unique by fixing the arbitrary constant to <em>U</em>.</li>

 <li>The Matlab codes m and idct.m on the course webpage compute the DCT and inverse DCT (these codes use the FFT to do the computation and are thus ‘fast’, although not as fast as they could be). Use these codes (or the equivalent codes in another language) and the procedure outlined in (a)–(c) to solve the problem from 4(c). Check your answer against the true solution <em>u</em>(<em>x</em>) = cos(2<em>x</em>). Plot the error in the approximate solution and report the relative two-norm of the error. Compare your solution from this problem to your solution from 3(c) above. You should find that they are the same (up to rounding errors).</li>

 <li>Extra credit (5 points): Why should the solution computed using the techniques from this problem be mathematically equivalent to the solution using the techniques from problem</li>

</ul>

3.