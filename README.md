Download link :https://programming.engineering/product/eecs205002-everyone-has-a-number/


# EECS205002-Everyone-Has-A-Number
EECS205002 Everyone Has A Number
Suppose we want to give each student a number based on his/her personal data, such as weight and hight. How can we do that? One simple strategy is to nd a weighted sum,

s = 1w + 2h;

that combines both factors. The question is how to decide the ratio between 1 and 2?

One solution is to perform the Principle Component Analysis (PCA) of the given data. Suppose we have N students, whose weights and heights are (w1; h1), (w2; h2), : : :, (wN ; hN ). The PCA computes a vector (1-D subspace), so that the data projected to it have the maximum variance, as shown in Figure 1. The solution of the vector is called the principle component of the given data.


Figure 1: The principle components of the given data.


Now let’s translate this problem to the language of linear algebra. Let xi = (wi; hi)T and the principle component be y = ( 1; 2), where kyk = 1. Recall the projection of xi to y is (see Section 5.1)

P xi = (yyT )xi = (yT xi)y = aiy:

where P = yyT is the projection matrix, and ai = yT xi is the coordinate of xi’s projection onto y. Now the problem of PCA becomes a one-dimensional variance maximization problem. Recall the basic statistics, the mean and the variance of a1; a2; : : : ; aN are

a =

1

N

ai and 2 =

1

N

(ai

a)2:

N

Xi

N

X

=1

i=1

So the problem of PCA can be expressed as

max

1

N (ai

a)2

(1)

k k

=1

N

Xi

y;

y

=1

It can be shown that (1) is equivalent to the following expression (why?)

k k

1

N

Xi

2

max

k

P (x

i

x)k

(2)

N

y; y =1

=1

where x is the mean of xi.

Let’s continue to work on the details of (2). The square of vector norm equals to the inner-product of itself, and P = yyT is the projection matrix. So

kP (xi

x)k2 = (xi

x)T P T P (xi

x)

= (xi

x)T yyT yyT (xi x)

= (xi

x)T yyT (xi

x)

We can do that becauseTy

T

y

2=1.

y = k

Tk

Next, since (xi

x)

y and y

(xi

x) are scalars, we can exchange those

two terms in their product and rewrite the above equation as

yT (xi

x)(xi

x)T y:

Let’s de ne the covariance matrix for the vector data xi as

=

1

N

(xi

x)(xi

x)T :

(3)

N

Xi

=1

For xi = (wi; hi)T , the covariance matrix is

= N

N

(wi

iw)(hi

2

h)

i

i=1

(w

(hiw)(hi)2

1

X

(w

w)

h h)


(20%) For each student, we have collect his/her personal data xi = (wi; hi; zi). https://forms.gle/3LZ1LKrAaJCZ3C1z6

(10%) Remove your own data from the list, and use other data to compute the PCA. Then use the mean and the principle component of other data to calculate your number.

(10%) Remove your own data from the list, and use other data to compute the PCA of 2D data rst, (wi; hi), and nd the weighted sum ti = 1wi + 2hi. Then compute the PCA of (ti; zi). Plot the gure of ti, zi, and their principle components, as Figure 1. Compare the results with (b). Will they give the same numbers? Discuss the reasons. (If they are the same, why? And if they are di erent, why?)

(20%) How to project the 3D data onto a 2D subspace so the variance of projected data are maximized? Design an algorithm, prove its correctness, and write a python code using the given data to show your algorithm works

pictorially. Your algorithm needs to nd an orthogonal basis of the 2D subspace Y = [y1 y2], Y T Y = I2. The de nition of 2D variance is

1

N

1

N

X

Xi

a = N

ai; 2 = N

ak2;

(6)

i=1

kai

=1

where ai is the projected xi from 3D to the 2D subspace, and a is their center (mean). The problem is to maximize 2.

Submissions

Write a report in a PDF le that includes (1), (2), (3), (4), and (5). For question (4), attach the plots and your discussion. For question (5), give your algorithm and proofs.

Python code of your implementation of (4) and (5).

Zip them and submit to iLMS system.
