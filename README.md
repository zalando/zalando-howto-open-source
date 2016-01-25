How to Open Source at Zalando
------------------------------------------------------------
Our guide to releasing an open-source project at [Zalando](https://www.zalando.com>), Europe's largest online fashion platform.

Open Source:
------------------------------------------------------------
- can improve quality
- can mitigate risks
- can increase trust
- can save us money, expand our technology choices, and help us remain cutting-edge
- is fun and makes us proud
- enables us to give back to the community, build our tech brand, and attract talent

Our Open Source First Principles
------------------------------------------------------------
- **Do “Open Source First”**: If your Zalando project can also be useful to non-Zalandos, release it as open source from the start.
- **Take Ownership**: Your team is responsible for ensuring that it’s possible to open source your project. Your delivery lead is available for guidance.
- **Share Your Code**: All code shared between teams must be open source.
- **Be Safe**: To ensure the broadest possible use of your project, use the MIT License only.
- **Deliver Quality**: Provide a great out-of-the-box experience.
- **Provide Documentation**: Include a clear README and default working configuration.
- **Stay Secure**: Make sure your project doesn’t include Zalando specifics, such as credentials and private identifiers.
- **Ask for Help**: Find colleagues to brainstorm ideas for your project and to review your work.
- **Promote**: Tell the world about your project via blog posts, social media and conference talks.
- **Join the Open Source Guild**: Help us make open source stronger at Zalando!

[Go here](https://zalando-open-source-principles.readthedocs.org/en/latest/) to read the accompanying docs.

What to Open Source, What Not to Open Source
------------------------------------------------------------
Never publish these as open source:
- PCI DSS-related projects: e.g. payment services
- Domain knowledge
- Anything that would risk our competitive advantage: confidential source code, recommendation algorithms, etc.
- Customer data
- Unique Selling Points (USPs)

If you're open-sourcing a project that has contained sensitive information in the past, the sensitive information can still be retrieved from the git commit history. Therefore, you should create an entirely new git repo for it before pushing it to GitHub.

**No issues? OK, go ahead and open source!** 
But ask yourself these questions, too:
- Will your project benefit others, including non-Zalando engineers? If your project is tightly coupled to our business, or doesn’t solve a problem, the community will likely view it as noise.
- Do you have time to maintain the code? If not, you can recruit help(ers) either internally or externally. Ask the Guild for assistance.
- Is your project infrastructure-related? These are usually easier to open source because they don’t touch our core business.
- Is your project a framework? These are also pretty safe for releasing publicly.

**Still unsure about what to do?**
If in doubt, ask your delivery lead.

**Equally simple guideline for delivery leads**:
If you’re in doubt, ask your department head. Management can work with Legal to determine Intellectual Property concerns.

Contributing to Non-Zalando Open-Source Projects
------------------------------------------------------------
We encourage you to contribute to other open-source projects in ways that benefit Zalando — for example, by making bug fixes in Apache, or submitting a patch to a language. Let the Guild know about your external contributions so we can help you get the recognition and support you deserve.

**Contributing to Google projects:** For typical CLAs, we are safe — but ask our legal team (guild can provide their contact info) to double-check whenever you’re in doubt. CLAs that are safe: Oracle, Apache. 

Working with External Contributors
------------------------------------------------------------
The Guild supports you in recruiting non-Zalandos to contribute to your project. We simply require that you have external contributors sign a contributor licensing agreement (CLA). A few good models to follow and adapt:
 - [.Net Foundation](https://cla2.dotnetfoundation.org/) example (electronic submission via GitHub account)
 - [Google’s CLA](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#-signing-the-cla) for contributing to AngularJS is a simple click-through form with a Googlebot that automatically checks for signatures
 - Selenium/Software Freedom Conservancy uses a [Google form](https://docs.google.com/a/zalando.de/forms/d/11Z8LoYpTGUIwCegifVH1YtL9smxVDNk-fOykUZTAWhE/viewform?hl=en_US&formkey=dFFjXzBzM1VwekFlOWFWMjFFRjJMRFE6MQ#gid=0)
 
Licensing
------------------------------------------------------------
To allow the most broad usage of our source code, and to keep open sourcing easy and safe for our developers, we only use the MIT license. MIT is succinct and straightforward, and allows for easy use in closed source projects as well. You do not even have to put a LICENSE file into your repository, as long as you use the correct MIT license URL. 

To reiterate: You must apply the MIT license to all newly created open source projects. If you fork other (external) projects or contribute to them, keep the original license.

**If Open-Sourcing a Library**: consider using a weak copyleft license, which won’t restrict the software that uses it to the same license; will allows usage in closed source software; and potentially increase the number of users and contributors.

Please do not use any other license without a very compelling reason. Licensing questions? Ask the Open Source Guild or our Zalando Legal team for help.

