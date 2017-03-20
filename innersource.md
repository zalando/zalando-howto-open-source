## How to InnerSource

### Preparing Your Repos for InnerSource
Many teams at Zalando have applied the InnerSource collaboration model to deliver more effectively and get work done. To try InnerSource with your own team's repos, here's what you need:

- **A good README**. What does your project do? What need does it address? Who inside Zalando would use it? How do you install it? Here’s [our README template](https://github.com/zalando/zalando-howto-open-source/blob/master/READMEtemplate.md) to help you.
- **Contribution Guidelines**. How do you want potential contributors to approach developing a change or enhancement for your project? An initial email? An empty pull request with a detailed proposal? [Here's a good set](https://github.com/zalando/skipper/blob/master/CONTRIBUTING.md) to help you get started.
- **A “Help Wanted” list**. Is it easy for other teams to spot the features, bugs, etc. you want help with? Issues Trackers are good, and tagging them with “help wanted” is even better. We have a Grafana dashboard collecting all our "help wanted" issues in one place [internal link, please ask us for it].
  - Compiling all your needs across all your InnerSourced repos in one email and blasting it out to our innersource Google group from time to time (or posting to zLive) is really great, too.
- **Github Enterprise**. Have you migrated from Stash yet? It helps if our code is all in the same system.
- **[Zappr](https://github.com/integrations/zappr)** up and running.
- **Adequate Test Coverage**. If you’re letting people contribute to your code base, you want to be reasonably confident that they (or you) don’t break the world when everything is integrated. Ping us here for help.
- **Continuous Integration**. Sure, you can run your test suite manually, but contributors will feel more confident in their changes if there’s a constant feedback loop. 

### FAQ on InnerSourcing Your Team's Repos

##### What if our team doesn't have time to review all the incoming PRs?
That's up to your team to resolve. But keep this in mind: What's faster, coding everything yourselves, or reviewing someone else's code? Approaching these efforts collaboratively — communicating your goals, wishes, risks, etc. to the team that's looking to contribute — can also save you lots of time. Talking things out over 30-60 minutes only takes 30-60 minutes.

##### But writing code is more fun than reviewing someone else's code. 
Maybe so. So write some code! Contribute a PR back to the team that contributed to your repo, or to a different team. Take a look at [our open-source offerings](https://zalando.github.io/) and code something for one of those projects.

##### Hey, it takes time to get people up to speed with the codebase and go through a couple of PR iterations to get something done. What if we don't have time right now to handle that?
Check again and make sure that it will truly take longer to teach someone about your codebase than to do the work yourself. Also, don't project or make assumptions about your potential, still-imaginary contributor: For all you know, they might be able to dive right in and get the job done quickly. They might even be able to teach you some things. This dynamic plays out in the open source world all the time.

##### What if we allow a team to go forward with a PR, and the end result is not to our liking?
Try to work with the contributing team to achieve something you can all accept. Remember, part of this is on you communicating with the contributing team what you're hoping they'll produce. Check in with them to get progress updates. Give them guidance, if needed. This will save you time, and save everyone involved disappointment.

##### What if someone surprises us with a PR we didn't ask for and don't want?
Then don't accept it. We want people to reach out to an owning team before making any bug fix or (especially) more significant change to a repo. If, for example, a team doesn't do that, and tries to fix one of your bugs/build one of your requested features without talking to you, then you have the right to reject their work. That team will most likely learn from the experience and be sure to talk about their proposed changes before setting to work. 

#### Changing Another Team's Repos
If your team needs something from another team's repo, InnerSource could help. A FAQ based on questions many a Zalando engineer has raised about how this works.

##### How do I know if a team will accept my proposed PR? 
Simple: Ask that team. We recommend reaching out to their producer or pinging them over HipChat as a first step. Don't do anything until you hear back from them. If they don't answer the first time, try them again.  

##### If my team/I change another team's repo, who ends up owning the repo?
The original team.

### More info
There's a growing number of useful resources on InnerSource. Here are a few:
- O'Reilly/PayPal's [Getting Started With InnerSource](https://www.oreilly.com/ideas/getting-started-with-innersource) booklet
- [Adopting Open Source Development Practices in Organizations: A Tutorial](http://ieeexplore.ieee.org/document/6809709/) by the IEEE (requires sign-in)
- [InnerSource Commons](https://paypal.github.io/InnerSourceCommons/) website
- [Inner Source in Platform-Based Product
Engineering](http://www.develop-group.de/fileadmin/dg_Internet/downloads/Fachveroeffentlichungen/Fachveroeffentlichungen_Projekt/devgroup_InnerSource_in_Platform-BasedProductEngineering.pdf) by Drs. Dirk Riehle, Maximilian Capraro, Detlef Kips, Lars Horn
