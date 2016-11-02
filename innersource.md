Many teams at Zalando have applied the InnerSource collaboration model to deliver more effectively and get work done. To try InnerSource with your repos, here's our how-to:

— **Create a good README**. What does your project do? What need does it address? Who inside Zalando would use it? How do you install it? Here’s [our README template](https://github.com/zalando/zalando-howto-open-source/blob/master/READMEtemplate.md) to help you.
— **Contribution Guidelines**. We How do you want potential contributors to approach developing a change or enhancement for your project? An initial email? An empty pull request with a detailed proposal? [Here's a good set](https://github.com/zalando/skipper/blob/master/CONTRIBUTING.md) to help you get started.
— **A “Help Wanted” list**. Is it easy for other teams to spot the features, bugs, etc. you want help with? Issues Trackers are good, and tagging them with “help wanted” is even better. We have a Grafana dashboard collecting all our "help wanted" issues in one place [internal link, please ask us for it].
  - Compiling all your needs across all your InnerSourced repos in one email and blasting it out to our innersource Google group from time to time (or posting to zLive) is really great, too.
— **Github Enterprise**. Have you migrated from Stash yet? It helps if our code is all in the same system.
— **[Zappr](https://github.com/integrations/zappr)** up and running.
— **Adequate Test Coverage**. If you’re letting people contribute to your code base, you want to be reasonably confident that they (or you) don’t break the world when everything is integrated. Ping us here for help.
— **Continuous Integration**. Sure, you can run your test suite manually, but contributors will feel more confident in their changes if there’s a constant feedback loop. 
