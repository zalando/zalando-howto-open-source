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
