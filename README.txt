[Kickstarter](http://www.kickstarter.com/) is an online crowdfunding platform for launching creative projects. When starting a new project, project owners specify a deadline and the minimum amount of money they need to raise. They receive the money (less a transaction fee) only if they reach or exceed that minimum; otherwise, no money changes hands. 

What's particularly fun about Kickstarter is that in contrast to [that other microfinance site](http://www.kiva.org/), Kickstarter projects don't ask for loans; instead, patrons receive pre-specified rewards unique to each project. For example, someone donating money to help an artist record an album might receive a digital copy of the album if they donate 20 dollars, or a digital copy plus a signed physical cd if they donate 50 dollars.

There are [a bunch](http://www.kickstarter.com/discover/hall-of-fame?ref=sidebar) of [neat](http://www.kickstarter.com/projects/1104350651/tiktok-lunatik-multi-touch-watch-kits) [projects](http://www.kickstarter.com/projects/2024077040/neil-gaimans-the-price), and I'm tempted to put one of my own on there soon, so I thought it would be fun to gather some data from the site and see what makes a project successful.

# Categories

I started by scraping the categories section.

[![Successful projects by category](http://dl.dropbox.com/u/10506/blog/kickstarter/successful-projects-by-category.png)](http://dl.dropbox.com/u/10506/blog/kickstarter/successful-projects-by-category.png)

In true indie fashion, the artsy categories tend to dominate. (I'm surprised/disappointed how little love the Technology category gets.)

# Ending Soon

The categories section really only provides a history of *successful* projects, though, so to get some data on unsuccessful projects as well, I took a look at the [Ending Soon](http://www.kickstarter.com/discover/ending-soon?ref=sidebar) section of projects whose deadlines are about to pass.

It looks like about 50% of all Kickstarter projects get successfully funded by the deadline:

[![Successful projects as deadline approaches](http://dl.dropbox.com/u/10506/blog/kickstarter/ending-soon-success.png)](http://dl.dropbox.com/u/10506/blog/kickstarter/ending-soon-success.png)

Interestingly, most of the final funding seems to happen in the final few days: with just 5 days left, only about 20% of all projects have been funded. (In other words, with just 5 days left, 60% of the projects that will eventually be successful are still unfunded.) So the approaching deadline seems to really spur people to donate. I wonder if it's because of increased publicity in the final few days (the project owners begging everyone for help!) or if it's simply procrastination in action (perhaps people want to wait to see if their donation is really necessary)?

Lesson: if you're still not fully funded with only a couple days remaining, don't despair.

# Success vs. Failure

What factors lead a project to succeed? Are there any quantitative differences between projects that eventually get funded and those that don't?

Two simple (if kind of obvious) things I noticed are that unsuccessful projects tend to require a larger amount of money:

[![Unsuccessful projects tend to ask for more money](http://dl.dropbox.com/u/10506/blog/kickstarter/successful-vs-unsuccessful-goal.png)](http://dl.dropbox.com/u/10506/blog/kickstarter/successful-vs-unsuccessful-goal.png)

and unsuccessful projects also tend to raise less money in absolute terms (i.e., it's not just that they ask for too much money to reach their goal -- they're simply not receiving enough money as well):

[![Unsuccessful projects received less money](http://dl.dropbox.com/u/10506/blog/kickstarter/successful-vs-unsuccessful-amount-pledged.png)](http://dl.dropbox.com/u/10506/blog/kickstarter/successful-vs-unsuccessful-amount-pledged.png)

Not terribly surprising, but it's good to confirm (and I'm still working on finding other predictors).

# Pledge Rewards

There's a lot of interesting work in behavioral economics on pricing and choice -- for example, the [anchoring effect](http://youarenotsosmart.com/2010/07/27/anchoring-effect/) suggests that when building a menu, you should [include an expensive item](http://www.neurosciencemarketing.com/blog/articles/neuro-menus-and-restaurant-psychology.htm), to make other menu items look reasonably priced in comparison, and the [paradox of choice ](http://en.wikipedia.org/wiki/The_Paradox_of_Choice:_Why_More_Is_Less) suggests that too many choices lead to a decision freeze -- so one aspect of the Kickstarter data I was especially interested in was how pricing of rewards affects donations. For example, does pricing the lowest reward at 25 dollars lead to more money donated (people don't lowball at 5 dollars instead) or less money donated (25 dollars is more money than most people are willing to give)? And what happens if a new reward at 5 dollars is added -- again, does it lead to more money (now people can donate something they can afford) or less money (the people that would have paid 25 dollars switch to a 5 dollar donation)?

First, here's a look at the total number of pledges at each price. (More accurately, it's the number of claimed rewards at each price.) [Update: the original version of this graph was wrong, but I've since fixed it.]

[![Pledge Amounts](http://dl.dropbox.com/u/10506/blog/kickstarter/pledge%20amounts.png)](http://dl.dropbox.com/u/10506/blog/kickstarter/pledge%20amounts.png)

Surprisingly, 5 dollar and 1 dollar donations are actually not the most common contribution.

To investigate pricing effects, I started by looking at all (successful) projects that had a reward priced at 1 dollar, and comparing the number of donations at 1 dollar with the number of donations at the next lowest reward. 

Up to about 15-20 dollars, there's a steady increase in the proportion of people who choose the second reward over the first reward, but after that, the proportion decreases.

[![Anchoring](http://dl.dropbox.com/u/10506/blog/kickstarter/anchoring.png)](http://dl.dropbox.com/u/10506/blog/kickstarter/anchoring.png)

[![Anchoring with Regression Lines](http://dl.dropbox.com/u/10506/blog/kickstarter/anchoring-abline-b.png)](http://dl.dropbox.com/u/10506/blog/kickstarter/anchoring-abline-b.png)

So this perhaps suggests that if you're going to price your lowest reward at 1 dollar, your next reward should cost roughly 20 dollars (or slightly more, to maximize your total revenue). Pricing above 20 dollars is a little too expensive for the folks who want to support you, but aren't rich enough to throw gads of money; maybe rewards below 20 dollars aren't good enough to merit the higher donation.

Next, I'm planning on digging a little deeper into pricing effects and what makes a project successful, so I'll hopefully have some more Kickstarter analysis in a future post.