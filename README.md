Thoughts on Concurrency from a Go perspective
====

#### Concurrency != Parallelism

While recently wanting to learn more about how Go makes the concept of concurrency easier to utilize I started by watching a few talks by the Go team. In particular, there are some great talks by Rob Pike specifically talking about how Go relates to both concurrency and parallelism.

I must first admit that I've been guilty of throwing these two terms around interchanegebly and after years of doing just that I found that it was actually pretty hard to divorce these two concepts from each other.  It is as if I have to undo the years of books, blogs, tutorials and conversations where these two words were sprinkled around by would-be expert programmers.

So exactly how do these two keywords differ?  From what I take away, the main difference is that with concurrency it's really about the building or composing of independantly executing parts.  And with paralellism, it's about the simeoultaneous execution of these individual parts. In other words, think of paralellism as hiring two clerks at your book store where they are both sorting books and putting them away at the same time. Instead of having just one person do the work, two people are doing it.  Two beings, with two separate brains, getting payed with two different pay checks.  The work of sorting and putting the books away is being done at possibly twice the speed assumming both clerks can sort and put away at roughly the same speed (with some assumptions of course.)

With the idea of parallelism alone, it almost seams like this is an obvious win.  Hire an extra clerk, more book-putting-away gets done and we move on with our lives. In fact, this too was how I thought for a long time. It turns out there is more to the story than just throwing more resources at the problem. You see, with another clerk, comes more responsibility on my part as a manager. I have to deal with two different personalities, two different needs, less profit possibly and anybody who's ever managed multiple people..it's not always easy making everything run smoothly.  There are other potential problems like what if there's only enough work for one person to sort and put books away?  What does the other person do?  Do they run the cash register?  They may not have the training.  Okay, I hope I made my point...we have another option when it comes to paralellism and that is concurrency.

Suppose we're back down to one clerk and that this clerk knows how to sort books and put them away and we'd like to additionally train this clerk to handle the cash register.  This actually might be a very good idea because maybe only a few customers trickle in every hour to rent some books and suppose a few customers trickle in every other hour to return those books they are done with. It would seam reasonable that our business may continue to operate with less overhead if we had our single clerk servicing these little tasks and breaking up their time accordingly.  In fact, I would argue that anytime there is a potential where somebody is waiting or standing around with nothing to do we could make better use of of our clerk and assign them little tiny tasks to handle before they just get exhausted and quit.

Example: I open my book business and I hire just one full-time clerk and I train them on the following tasks that I'm comfortable for them to do:

* Open up shop
* Make coffee in the morning
* Check mail
* Service customer's renting books
* Service customer's returning books
* Make coffee in the afternoon
* Close up shop


```go
func whoaNo(){
	fmt.Println("whoaaa....nooooo!")
}
```
