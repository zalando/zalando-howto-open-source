How to Open Source at Zalando
------------------------------------------------------------
A guide to releasing an open-source project at [Zalando](https://www.zalando.com>), Europe's largest online fashion platform.

Why Open Source? Because It Can:
------------------------------------------------------------
- improve quality
- mitigate risks
- increase trust
- save us money
- expand our technology choices
- be fun 
- enable us to give back to the community
- strengthen our tech brand
- attract talent

Our Open Source First Principles
------------------------------------------------------------
- **Do “Open Source First”**: If your Zalando project can also be useful to non-Zalandos, release it as open source from the start.
- **Take Ownership**: Your team is responsible for ensuring that it’s possible to open-source your project. Your delivery lead is available for guidance.
- **Share Your Code**: All code shared between teams must be open source.
- **Be Safe**: To ensure the broadest possible use of your project, use the MIT License only.
- **Deliver Quality**: Provide a great out-of-the-box experience.
- **Provide Documentation**: Include a clear README and default working configuration.
- **Stay Secure**: Make sure your project doesn’t include Zalando specifics, such as credentials and private identifiers.
- **Ask for Help**: Find colleagues to brainstorm ideas for your project and to review your work.
- **Promote**: Tell the world about your project via blog posts, social media and conference talks.
- **Join the Open Source Guild**: Help us make open source stronger at Zalando!

[Go here](https://zalando-open-source-principles.readthedocs.org/en/latest/) to read the accompanying docs. [This blog post](https://tech.zalando.com/blog/zalando-techs-new-open-source-principles/) might also be of interest.

What to Open Source, What Not to Open Source
------------------------------------------------------------
##Never open-source these:
- PCI DSS-related projects: e.g. payment services
- Domain knowledge
- Anything that would risk our competitive advantage: confidential source code, recommendation algorithms, etc.
- Customer data
- Unique Selling Points (USPs)

If you're open-sourcing a project that has contained sensitive information in the past, the sensitive information can still be retrieved from the git commit history. Create an entirely new git repo for it before pushing it to GitHub.

**No issues? Great! On to the next section ...

##Open Source Workflow

###Creating a new project
Creating a new open source project should almost always be a team decision. This is because maintaining a project requires commitment, time, and resources. Before starting a new project, ask these questions:
- Does the project already exist? (Do research so you can avoid reproducing an existing effort.)
- Who is the audience?
- Who will be a maintainer? 
     - We require at least one. 
- Will you try to build community around the project?
     - Internal community: This is very important. Promote your project to as many Zalando teams as possible so they can      consider using it. The internal success of a project can give you a good idea about its potential to be adopted/used externally. 
     - External community: If you’re not eager to promote your project to the public, keep it internal.
 
If you want to launch a new project separate from your team, talk to your delivery lead first. Let them know about your plan. Then ask yourself the questions immediately above.

###"Truly Open Source": How-To and Tips  
Our open source work should reflect and reinforce the principles of Radical Agility:
- Autonomy: We support teams and individuals who contribute to open source
- Mastery: Our projects reflect a high level of quality, thoughtfulness, and skill
- Purpose: Our projects are useful to our team, and to the community at large

####Getting & Keeping Your Project on Our Main Org Page
#####Criteria
The “Open Source First” principles we’ve established encourage you to code in public from the very beginning of your project. Your code doesn’t have to be perfect before you open-source it.  

That said, to appear on github.com/zalando (our main org page) your project should be “truly open-source,” or aimed at becoming so. This means:
- it’s useful and interesting to non-Zalandos. It might serve an entire language community, users of specific tools (Docker, Maven, etc.), or some other group. 
- it’s useable out of the box and independent of our systems
- it has a clear README that:
    - enables non-Zalando devs to download, install, run and use the project with minimal friction (because you’ve been   thorough in your detail)
    - invites contributors via a TODO list 
- You respond promptly (within 72 hours) to PRs, issues, and queries

These criteria are meant to help drive the adoption, use and overall success of your work—not to impose restrictions. 

#####How to Make Your Project “Truly Open Source”

Some tips:
- In the earliest stages of development, define what the project will do and not do as clearly as possible. Think of it as a product: What is its purpose?
- Identify potential users/audience. Who will use it? How broadly can you promote it?  
     - Our tech team is a great focus group. Ask your colleagues for input and feedback. 
- Ask yourself: Will you want to be working on/maintaining it six months from now? A year from now? Who else can maintain the project with you? 
- Build community: If a project is in development, list unfinished features/components in the “TODO” of your README and in your conversations with potential contributors.
- Before releasing your project, ensure that the README is clear enough for potential contributors and users to understand what it does and the problem(s) it solves.

Not sure about your project’s usefulness? The Open Source Guild, your team, your delivery lead, LinkedIn groups, community forums/boards, and Meetup audiences can all be great sources of info.  


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
To allow the most broad usage of our source code, and to keep open-sourcing easy and safe, we use [the MIT license](https://opensource.org/licenses/MIT). MIT is succinct, straightforward, and easy use in closed-source projects.  

To reiterate: You must apply the MIT license to all newly created open-source projects. If you fork other (external) projects or contribute to them, keep the original license.

**If Open-Sourcing a Library**: consider using a weak copyleft license that won’t restrict the software that uses it to the same license; will allow usage in closed source software; and will potentially increase the number of users and contributors.

Please do not use any other license without a very compelling reason. Licensing questions? Ask the Open Source Guild or see our TechWiki page (internal doc) for the link to more detailed information about licensing.

If your team uses an external project whose license is not Zalando-recommended, you can can use GPL code — but only internally. Be sure it's a version of the GPL that continues to allow for the ASP loophole. AGPL and versions of the GPL with additional restrictions won't work.

**Who is the license owner?**

Zalando SE.

**LICENSE document**

Every project needs a ‘LICENSE’ file at the root of the repository that contains the copy of the selected license (see above). [Here is an example](https://opensource.org/licenses/MIT) for MIT.

**README note**

Every README{.md,.rst} file must state the following at the end:

>The MIT License (MIT)
>Copyright © [yyyy] Zalando SE, https://tech.zalando.com

>Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

>The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

>THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
>

Replace the [yyyy] field with the year that you created the project, and do not update it. Do not provide multiple years.

**Still unsure about what to do?**

If in doubt, ask your delivery lead.

**Equally simple guideline for delivery leads**:

If you’re in doubt, ask your department head. Management can work with Legal to determine Intellectual Property concerns.

**Repository of meta information**

Many package managers include a feature to make the applied license machine readable. Use these! An example for [Maven](https://maven.apache.org/pom.html#Licenses):

 ```<licenses>
 <license>
   <name>MIT</name>
   <url>https://opensource.org/licenses/MIT</url>
   <distribution>repo</distribution>
  </license>
 </licenses>
 ```
An example for [Node](https://docs.npmjs.com/files/package.json#license), according to [this](https://gist.github.com/robertkowalski/7620849):

```
“license”: “MIT”
 ```
An example for Scala (with sbt):
```
licenses += ("MIT", url("http://opensource.org/licenses/MIT"))
```
Restrictions Imposed by the License
------------------------------------------------------------
“Dependency” typically means “being linked with,” “included in your artifact,” or “depends on it during runtime.” Dependencies can limit you. To remain in compliance, check the licenses of your projects. Your build tool’s license does not affect your software’s license. A jar file or Python dependency will affect your software.

*There is no license*

A project always has a license. If there is no license statement, the author automatically receives a copyright. [This](http://choosealicense.com/no-license/) implies that no one has the right to modify or redistribute the software. If you really need the software, contact the author (who is likely unaware) and ask him/her to provide a proper license.

*Unusual additions*

As stated by Zalando Legal, it is OK to use React and other Facebook open-source software projects for Zalando projects.

Official Repositories
------------------------------------------------------------
Some guidelines:
- Host **all** source code in [the ‘zalando’ space](https://github.com/zalando) on GitHub.
- GitHub organization owners must enable [Two-Factor Authentication (2FA/MFA)](https://help.github.com/articles/about-two-factor-authentication/).
- Host JVM artifacts (*.jar) on Maven Central in [the ‘org.zalando’ group](https://repo1.maven.org/maven2/org/zalando/).  To do this, get a [Sonatype](http://central.sonatype.org/) account and ask the STUPS team to add it to Zalando.
- Host Python packages on [PyPI](https://pypi.python.org/pypi/) (PyPI has no namespaces) and make sure that multiple persons have “maintainer” rights.
- Publish SBT plugins [on Bintray](https://bintray.com/zalando). An example of the publishing process is [here](http://www.scala-sbt.org/0.13/docs/Bintray-For-Plugins.html); these SBT files ([#1](https://github.com/zalando/swagger-speccer/blob/master/build.sbt) and [#2](https://github.com/zalando/swagger-speccer/blob/master/project/bintray.sbt)) illustrate the publishing configuration.
- [Node](https://www.npmjs.com/) modules [now have namespaces](http://blog.npmjs.org/post/116936804365/solving-npms-hard-problem-naming-packages). We prefix them with our (hopefully short!) product name — e.g. [karma](https://karma-runner.github.io/0.12/index.html) plugins are prefixed “karma-”; the same goes for gulp, grunt, etc. Host your Node modules in the public NPM registry. Here is [how to publish to NPM](https://gist.github.com/coolaj86/1318304).
- For Docker images: You can currently browse it [here](https://registry.opensource.zalan.do/ui/), or with the Pier One command line utility. We have an [open source registry](https://registry.opensource.zalan.do/ui/) that everyone can read. It is deployed in the AWS open source account and Docker images can be pushed by any team member to their respective team repo:

```bash
$ # you need to login to registry-write.opensource.zalan.do (workaround for Docker V2 bug)
$ pierone login --url registry-write.opensource.zalan.do
$ docker push registry-write.opensource.zalan.do/myteam/myartifact:1.0
$ # on any other computer:
$ docker pull registry.opensource.zalan.do/myteam/myartifact:1.0 # no auth needed for download!
```

Open Source Workflow
------------------------------------------------------------
**Creating a new project**

Creating a new open source project should almost always be a team decision. This is because maintaining a project requires commitment and time, and your team needs to prioritize and allocate resources. If you are an individual who wants to launch a new project individually, talk to your delivery lead first and let them know about your plans.

**Official Maintainers**

Every project needs at least one dedicated maintainer (contact person). List the maintainer(s) of your project (including email) in the MAINTAINERS file. Only maintainers can package new versions and apply changes to the repository (i.e., merging pull requests). [This helper script](https://github.com/zalando-stups/github-maintainer-cli) will enable us to keep an overview of repos that users are maintainers for.

The Open Source Guild reserves the right to contact maintainers to ensure their project is still active. If the project is dormant, we will work with you to either find a new maintainer or take the project off our organization page.

Every project needs a ‘[MAINTAINERS](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/tree/MAINTAINERS)’ file (listing all maintainers) at its root. Your build/packaging configuration file (e.g., [pom.xml for Maven](https://maven.apache.org/pom.html#Developers)) can fulfill the purpose of a MAINTAINERS file. Format:

     [full name] <email address>
     [second full name] <email address>
     etc.

Please note that our Catwatch application [will collect maintainers from the MAINTAINERS files](https://github.com/zalando/catwatch/issues/29).

**Official Namespace**

The official namespace for our projects is ‘**org.zalando**’, where applicable.

**Applying Changes**

All repository changes, including those made by maintainers, should come from GitHub pull requests so that we can streamline review and change tracking (as per [GitHub Flow](https://guides.github.com/introduction/flow/)). Everyone should have their own fork, though you can still edit READMEs/documentation/related files with the GitHub “Edit” button. The ‘master’ branch should be the accepted development head; pull requests get merged there.

**Versioning**

All project artifacts should be [versioned semantically](http://semver.org/). Tag all versions in GitHub with the exact version name (like ‘0.1.0’, i.e. do not prefix tags with “v.” or similar). For a better user experience, use the GitHub “release notes” feature to add notes whenever you change something in the new version.

**Documentation**

Markdown is the simplest and most easily understood syntax, which is why it’s so common on GitHub; we recommend using it for all your documentation. However, we realize that there are exceptions: PyPi, for example, uses reStructuredText, and the Python community in general doesn’t use Markdown. If Markdown isn’t practical, then we recommend using only one markup format in your project. The format you choose should be [GitHub-supported](https://github.com/github/markup#markups).

Documentation should mainly cover all technical details and configuration options, and must include a README.md file with the following:
 - a small description of what the project is and does
 - where to find additional and more advanced documentation (optional)
 - a usage description or configuration
 - directions on how to build, test, package and release the project
 - a ‘LICENSE’ file

*Some tips*
- State at the beginning what the project does and what problem(s) it solves.
- Keep your docs short and sweet.
- Break up text often.
- Think about SEO.
- Create a TODO list and update it based on issues and desired features; add level-of-difficulty cues to onboard contributors at the suggested levels of skill.
- If you need to include more content than the average README does, provide the link to your more detailed documentation.

http://zalando.github.io/, aka "CatWatch"
------------------------------------------------------------
All Zalando open-source projects are listed on [zalando.github.io](http://zalando.github.io/) (also called [CatWatch](https://github.com/zalando/catwatch)): our own metrics dashboard measuring our most popular public projects and our most active contributors in terms of commits, stars and forks. Please add a [.catwatch.yaml file](https://github.com/zalando/zmon/blob/master/.catwatch.yaml) to the root of your repository to set a human-readable project title and image URL.

Review
------------------------------------------------------------
Ask your team and other peers to review your code and install and test your project prior to public release. Peer review tends to be more effective than unit testing. Not sure what to ask for, or how to peer-review? This list of [11 best practices](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/) should help.

Our basic quality criteria for open-source projects:
 - Is the project useful to others, including non-Zalandos?
 - Is the documentation clear and comprehensive?

