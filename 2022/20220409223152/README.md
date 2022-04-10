# The Law of Triviality

I came across this concept a few months ago, and it fit *so well* with what I experienced at 
Cerner. [The law of triviality](https://en.wikipedia.org/wiki/Law_of_triviality) is an argument that
when people are confronted with a difficult/complex task, they will focus on giving critique to the
simple, easy to grasp tasks. This is sometimes called bike-shedding, referencing that when reviewing
the plans for a nuclear energy plant, people would focus on talking about a trivial problem that is
easy to critique: the bike shed.

My experiences at Cerner, particularly with design and code reviews, fits this argument perfectly.
I remember code reviews with lots of nitpicky comments:

- Move this variable declaration up.
- The order of parameters for this new function should be different.
- Don't end comments with a period.
- Name this variable `FilterBookTableResultsByAuthorName` instead of `FilterBooksByAuthor`.

I will say that while these individual comments may not be important, they are still important to be
made and addressed -- after a long enough time of ignoring these issues, the codebase runs out of
control. One of our services at Cerner had a mixture between three and four spaces across files and
sometimes even within the same file, for example.

The problem is that I wanted advice on the *design* of the code, not variable names, and everyone
only wanted to spend a few minutes glancing at the syntax instead of the design. Leaving feedback on
the design requires far more time. I understand why I didn't get suggestions on the design -- there
aren't many ways to do what I was doing, no one has time other than to look at the green and red
lines of the diff, and as long as it gets done, who cares?

This seems like I'm saying we can't afford the time to comment on design, or we shouldn't leave
*bike-shedding comments* on code reviews. Not at all, this zettel is more of a elongated thought
about knowing when you are bike-shedding or not. Did I comment on the design, or did I only mention
that there should be one line here instead of two? Code reviews ought to be more than a stamp, they
ought to strive to enable the team to work quickly, efficiently, and cleanly in the future.

#FutureBlog #SoftwareEngineering #WorkBehaviors

