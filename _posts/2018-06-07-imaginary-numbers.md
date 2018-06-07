---
layout: post
title: "ELI5: Complex and imaginary numbers"
categories: eli5
---

Reddit's "explainlikeimfive" or ELI5 subreddit has many great descriptions that describe complex concepts in simple ways.

I enjoyed this short summary (by the user pdpi) describing the motivation behind the concept of complex and imaginary numbers [[source](https://www.reddit.com/r/explainlikeimfive/comments/10h7nl/eli5_complex_and_imaginary_numbers/c6dymfd)]:
> When I teach this, I force students to go back to earlier sets that were not closed under our operations: (the word constructed stands in for constructed/discovered/invented")
>
> The naturals are not closed under subtraction, so we constructed 0 and negatives.
>
> The integers are not closed under division, so we constructed rationals.
>
> The rationals are not closed for for problems such as the ratio of C/d in a circle or the diagonal of a square, so we constructed irrationals to complement the rationals and create the real numbers.
>
> Finally, the reals are not closed for polynomials such as x² + 1 = 0, so we have need of more numbers. The definition of i = sqrt(-1) is no different an invention than the definition that 0 = x - x.
>
> The consequences of such a definition are nicely outlined by your post, but in alluding to previous number sets and their non-closure I find a lot of success.

It was written in response to the top-rated comment. This amazing explanation (by the user GOD_Over_Djinn) is much longer, but covers the concept from the ground up in a simple and clear manner [[source](https://www.reddit.com/r/explainlikeimfive/comments/10h7nl/eli5_complex_and_imaginary_numbers/c6djd3z)]:

> Long answer ahead.
>
> This won't be like you're five, but it won't be like you're a math grad either. I'll assume no advanced knowledge on your part—just a sincere desire to learn and the ability to follow along a little bit. The first step is to forget everything that you've ever heard about the mysterious imaginary number i. Talking about "imaginary numbers" and specifically i can be a useful shorthand, but in my opinion it's only useful after you get some extreme basics down which justify the creation of this quasi-mystical beast i and the rest of the imaginary numbers. Typical introductions to this start with "well there is no square root of -1 in the real numbers but like, there is one and it's i and that seems weird cause there's not but there really is so let's just go with it and see what happens" and to me that was always utterly unsatisfactory and now that I understand these things better I want to explain it to you the way I think it ought to be taught.
>
> So forget all this i business, forget all this z=a+bi business, all this square root of -1 business, all of it. A complex number is nothing but an ordered pair of real numbers (a,b). So like, (1,0) is a complex number, (0,1) is a complex number, (-100,100) is a complex number, (π,-e) is a complex number, and so on. The set of complex numbers is just the set of coordinates on a plane, just like you've seen a million times before.
>
> So what distinguishes a complex number from just any old pair (x,y) of real numbers? The key distinction comes not from the numbers themselves, but from the way that two complex numbers interact with each other. In particular, in order to define C, the [field](http://en.wikipedia.org/wiki/Field_(mathematics)) of complex numbers, we need to say exactly what is meant by addition and multiplication of complex numbers.
>
> Addition is easy. If x=(a,b) and y=(c,d) are complex numbers, then x+y=(a+c,b+d). So for example, (2,3)+(4,5)=(6,8).
>
> Multiplication is a little tricker, and is actually the heart of what makes the complex numbers unique. We define multiplication between complex numbers x=(a,b) and y=(c,d) to work as follows:
>
> x*y=(ac-bd,ad+bc)
>
> So, for example, (2,3)*(4,5)=((2)(4)-(3)(5),(2)(5)+(3)(4))=(-7,22). That's weird. But, and I would encourage you to try this out to check, it behaves exactly in the ways that we would like something called "multiplication" to behave. In particular, it obeys the following rules:
>
> 1. For complex numbers x and y, x*y=y*x.
> 2. For complex numbers x, y, and z, x*(y*z)=(x*y)*z.
> 3. For complex numbers x, y, and z, x*(y+z)=x*y+x*z.
>
> It's weird and it feels like we pulled the definition of multiplication out of a hat, but at least we can understand what a complex number is and what multiplication is, and it's all defined in terms of stuff that we already know works fine in real numbers.
>
> So we have this new mathematical system called the complex numbers that we've built out of ordered pairs of real numbers and probably it would be nice to investigate it a little bit further. Here's a very important feature of this new complex number system: complex numbers of the form (a,0), where a is a real number, behave in a very nice way. In particular, let's let x=(a,0) and y=(c,0) be complex numbers. Now, by following the rules above, we can see the following:
>
> x+y=(a+c,0+0)=(a+c,0)
>
> (this one is a little more surprising) x*y=(ac-(0)(0),a(0)-0(c))=(ac,0).
>
> What's interesting about this? Well think about the real numbers a and c. When we add a and c, we end up with some number a+c. Now, when we add the complex numbers (a,0) and (c,0), we end up with some complex number (a+c,0). When we multiply a and c in the real numbers, we get ac, and when we complex-multiply (that's a term I just made up for the weird "multiplication" that we defined to be part of complex multiplication) the numbers (a,0) and (c,0) we get (ac,0).
>
> So in a (very important, fundamental) way, the real number a corresponds to the complex number (a,0). We can add and multiply complex numbers that look like (a,0) and it's essentially no different from adding and multiplying real numbers. In this way, we can think of the complex numbers that we've invented as "containing" the real numbers, in the sense that anything that you can do with the real numbers a and c will correspond to something equivalent that you can do with the complex numbers (a,0) and (c,0).
>
> Now here's the big kicker. Consider the complex number (0,1). In particular, we're going to look at what happens when you square (0,1). Using the definition of multiplication, we get
>
> (0,1)*(0,1)=((0)(0)-(1)(1),(0)(1)+(1)(0))=(-1,0).
>
> And by what we just established in the last part, we know that (-1,0) corresponds in a special way to the real number -1. So we've found the first really interesting property of this new complex number system: it offers us a square root of -1. What that really means is that there is a complex number (0,1) with the property that when you multiply it by itself, it gives you the complex number (-1,0) which corresponds to the real number -1.
>
> Now, for no reason whatsoever other than tradition, we might decide to call this special complex number (0,1) i, and we might refer to it as something silly like "the imaginary constant". If, along with i, we define the number 1=(1,0), then we can write any complex number we like in terms of 1 and i. So for instance, we can write the complex number (3,4) like this: 31+4i=3(1,0)+4(0,1)=(3,0)+(0,4)=(3,4). And, bearing in mind the connection between numbers of the form (a,0) and real numbers, we can say that this number has a "real part" (3,0) and, just for the sake of tradition, an "imaginary part" (0,4).
>
> And if we can all agree that the 1 is implied whenever you see something that looks like a1+bi, then we can save some paper by just omitting it and saying that a+bi is just another way of writing the complex number with real part a and imaginary part b. So (a,b) and a+bi are just completely equivalent ways of writing the same thing.
>
> Why do we need equivalent ways of writing the same thing? Mostly because sometimes things that are hard to see when you write them in one way can be easy to see when you write them in another. In particular, the multiplication seems to make a lot more sense in this context. The very weird, counterintuitive, almost magical definition of multiplication that we came up with in the ordered pairs world ends up feeling very natural in the a+bi world. This stems from the fact that i²=-1 (remember, i²=-1 is shorthand for "the complex number i, when complex-multiplied by itself, gives us a complex number (-1,0) which corresponds to the real number -1"). So let x=a+bi and y=c+di be complex numbers—the complex numbers (a,b) and (c,d) respectively. Now when we multiply them it looks like this:
>
> (a+bi)(c+di)
>
> We can FOIL this bad boy like we're in grade 11:
>
> (a+bi)(c+di) = ac + adi + bci + bdi²
>
> Now, recalling that i² is the same as -1, we can write that as
>
> ac + adi + bci - bd
>
> And organizing back into the nice form we are using for complex numbers, we get
>
> ac-bd + (ad+bc)i
>
> Which, as we've defined, corresponds to the real number (ac-bd,ad+bc)—the exact formula that we defined above for multiplication! Of course, this shouldn't be surprising. Multiplication is the way it is because that's how we defined it to be. But somehow, by recognizing that i²=-1, the multiplication suddenly seems like a natural extension of the multiplication that we're used to for real variables, rather than just a formula that was pulled out of thin air.
>
> In my opinion, this is the right way to approach the subject. The motivation is clear and everyone knows it: we would like some kind of system which gives square roots to negative numbers. But I think the wrong way to go is to say, "okay, well let's just conjure it into existence and call it i and just go from there". What we want is a system which is borne out of reasonable extensions to things that we already have, like real numbers and ordered pairs and multiplication and addition. We want to figure out what we would have to build in order to get the mysterious i, rather than assuming i exists and going from there. i²=-1 is the goal, not the starting point.
