How to Open Source at Zalando
==================

A guide to releasing an open-source project at [Zalando](https://www.zalando.com>), Europe's largest online fashion platform.

Table of Contents
------------------------------------------------------------

  - [Why Open Source?](#why-open-source)
  - [Our Open Source First Principles](#our-open-source-first-principles)
  - [To Open Source, or Not to Open Source?](#to-open-source-or-not-to-open-source)
    - [Never Open-Source These](#never-open-source-these)
    - [Doing Open Source: Project Workflow](#doing-open-source-project-workflow)
        - [Before You Start Coding](#before-you-start-coding)
        - [The Main Zalando Repository: For the "Truly Open Source"](#the-main-zalando-repository-for-the-truly-open-source)
        - [The Incubator: For the Open-Source, But Not "Truly Open Source"](#the-incubator-for-the-open-source-but-not-truly-open-source)
       - [Using GitHub Enterprise (GHE)](#using-github-enterprise-ghe)
  - [Open-Source Basics](#open-source-basics)
    - [Code Review](#code-review)
    - [Creating a README](#creating-a-readme)
      - [Do](#do)
      - [Don't](#dont)
      - [Syntax and Formatting](#syntax-and-formatting)
    - [Official Namespace](#official-namespace)
    - [Applying Changes](#applying-changes)
    - [Versioning](#versioning)
    - [Maintainers](#maintainers)
      - [Create a Maintainers File](#create-a-maintainers-file)
      - [Be Prompt and Responsive](#be-prompt-and-responsive)
      - [Use Issues Creatively](#use-issues-creatively)
    - [Stay Secure](#stay-secure)
      - [Two-Factor Authentication Is Required](#two-factor-authentication-is-required)
    - [About Licensing](#about-licensing)
      - [Quick FAQ](#quick-faq)
        - [Which License Do We Use?](#which-license-do-we-use)
        - [Must I Use MIT?](#must-i-use-mit)
        - [I don't like the MIT license. Can I use another license?](#i-dont-like-the-mit-license-can-i-use-another-license)
        - [What if I fork an external project and/or contribute to it?](#what-if-i-fork-an-external-project-andor-contribute-to-it)
        - [I'm open-sourcing a library. What should I do?](#im-open-sourcing-a-library-what-should-i-do)
        - [What if my team uses an external project whose license is not Zalando-recommended?](#what-if-my-team-uses-an-external-project-whose-license-is-not-zalando-recommended)
        - [Who is the license two-factor?](#who-is-the-license-two-factor)
        - [Does my project need a LICENSE file?](#does-my-project-need-a-license-file)
        - [Do I need to add a license header to every source file?](#do-i-need-to-add-a-license-header-to-every-source-file)
        - [What about a README note?](#what-about-a-readme-note)
        - [I still have licensing questions. What can I do?](#i-still-have-licensing-questions-what-can-i-do)
        - [But I am a delivery lead.](#but-i-am-a-delivery-lead)
        - [But I am a department head.](#but-i-am-a-department-head)
      - [Repository of Meta Information](#repository-of-meta-information)
      - [Restrictions Imposed by the License](#restrictions-imposed-by-the-license)
        - [Unusual Additions](#unusual-additions)
      - [There Is No License](#there-is-no-license)
    - [Other Repository Information](#other-repository-information)
      - [JVM artifacts](#jvm-artifacts)
      - [Python packages](#python-packages)
      - [SBT plugins](#sbt-plugins)
      - [Node modules](#node-modules)
      - [Docker images](#docker-images)
    - [Working With External Contributors](#working-with-external-contributors)
    - [Make Forks Meaningful](#make-forks-meaningful)
    - [Deprecate Responsibly](#deprecate-responsibly)
      - [How to Deprecate](#how-to-deprecate)
      - [Tips for Finding a New Owner](#tips-for-finding-a-new-owner)
    - [Project Promotion](#project-promotion)
      - [Catwatch](#catwatch)
      - [Proactively Communicate](#proactively-communicate)
- [Contributing to Non-Zalando Open-Source Projects](#contributing-to-non-zalando-open-source-projects)
      - [General](#general)
      - [Google Projects](#google-projects)

###Why Open Source?

Because It Can:

- improve quality
- mitigate risks
- increase trust
- save us money
- expand our technology choices
- be fun
- enable us to give back to the community
- strengthen our tech brand
- attract talent

##Our Open Source First Principles

**Vision**: 
*We strongly believe that open source software benefits the tech community, and that providing broadly useful code to the world is a virtue. We strive to work in an open source way to the betterment of Zalando and the world.*

- **Do “Open Source First”**: If your Zalando project can also be useful to non-Zalandos, release it as open source from the start.
- **Take Ownership**: Your team is responsible for ensuring that it’s possible to open-source your project. Your delivery lead is available for guidance.
- **Share Your Code**: All code shared between teams must be open source.
- **Be Safe**: To ensure the broadest possible use of your project, use the MIT License only.
- **Deliver Quality**: Provide a great out-of-the-box experience.
- **Provide Documentation**: Include a clear README and default working configuration.
- **Stay Secure**: Make sure your project doesn’t include Zalando specifics, such as credentials and private identifiers.
- **Ask for Help**: Find colleagues to brainstorm ideas for your project and to review your work.
- **Promote**: Tell the world about your project via blog posts, social media and conference talks.
- **Join the Open Source Guild**: Help us make open source stronger at Zalando! Come on, it'll be fun. :)

[This blog post](https://tech.zalando.com/blog/zalando-techs-new-open-source-principles/) might also be of interest.

To Open Source, or Not to Open Source?
------------------------------------------------------------

###Never open-source these:

- PCI DSS-related projects: e.g. payment services
- Domain knowledge
- Anything that would risk our competitive advantage:
  - confidential source code
  - recommendation algorithms
- Customer data
- Unique Selling Points (USPs)

If you're open-sourcing a project that has contained sensitive information in the past, the sensitive information can still be retrieved from the Git commit history. Create an entirely new Git repo for it before pushing it to GitHub.

No issues? Great! On to the next section ...

##Doing Open Source: Project Workflow
Our open source work should reflect and reinforce the principles of Radical Agility:
- **Autonomy**: We support teams and individuals who contribute to open source
- **Mastery**: Our projects reflect a high level of quality, thoughtfulness, and skill
- **Purpose**: Our projects are useful to our team, and to the community at large

###Before You Start Coding
Creating a new open source project should almost always be a team decision. This is because maintaining a project requires commitment, time, and resources. Before starting a new project, ask these questions:
- What will the project do and not do? What is its purpose? What is it trying to solve?
- Does the project already exist?
  - Do some research to avoid reproducing an existing effort.
- Who is the audience?
  - Our tech team is a great focus group. Ask your colleagues—the Open Source Guild, your team and delivery lead, other teams—for input, interest and feedback.
- Who will be a maintainer?
     - We require at least one.
- Can you envision working on/maintaining it six months from now? A year from now?
- Will you build community around the project?
   - Internal community: This is very important. The internal success of a project can give you a good idea about its potential to be adopted/used externally.
   - External community: Who in your network would be willing to contribute?
   - Sources
       - LinkedIn groups
       - community forums/boards
       - Meetup audiences
     - Will you need contributors with a different skillset to finish the project?
     - Create a “TODO” in your README to invite contributions.

If you want to launch a new project separate from your team, talk to your delivery lead first. Let them know about your plan. Then ask yourself the questions immediately above.

###Open Source, Coding in the Open, and InnerSource
Based on quality, usefulness and maintenance considerations, we use this matrix to decide how to classify and place our projects:

- InnerSource = GitHub Enterprise
- Coding in the Open = Incubator
- Open source = main Zalando org

In the inverse, you could think of these three categories as “steps” for your project as it develops from an idea to a minimum viable product (MVP) that someone on the outside could understand, use and possibly work on as a contributor. 

The next sections offer more details on differences between open source, “coding in the open” and InnerSource.

###What Makes a Project “Open Source”
An open source project:
- **is useful beyond Zalando**. It is free of Zalando dependencies and simple for a non-Zalando to install and start using.
- **has high-quality documentation** that is up-to-date and clear about what the project does. (This template can help you.)
- **is tested**. It has automated tests and takes advantage of test coverage.
- **is under active development**, or is stable enough to be considered a “finished” product. If the project is incomplete, at least one maintainer has worked on it in the last three months. If it’s stable and doesn’t require constant maintenance, you’ve stated as much in your README.
- **is innovative**. If it duplicates an existing project, it does at least one thing better, faster, differently, etc., or is higher-quality.
- **meets our non-negotiable guidelines** regarding security and compliance. 
- **is an MVP**. It either meets or surpasses “minimum viable product” status. An outside developer could use it and even contribute to it. If it’s buggy or very early-stage, it includes a brief development status in the intro stating as much. (This template can help you.)
- **has a plan**. Its maintainers care about making it a success. They commit to responding to PRs and issues in a timely manner (48-72 hours), thank contributors, and convert quality contributors to trusted maintainers as appropriate.

**Example projects**: Patroni, Connexion, Zappr, NSEnter, Tailor, Spoton.
**Where it belongs**: Zalando main org

We have also published some document-only repositories like our RESTful API guidelines, our “How to Open Source” guidelines, the Tech Radar, and our Rules of Play. These reflect our organizational perspective on technical topics, and are therefore of potential interest to other companies who are looking for ideas and case studies. We should keep them limited in number and broad in scope.

### What Makes a Project “Coding in the Open”

“Coding in the open” is how we describe a Zalando project that is already public—or that you want to make public for personal reasons—but not currently useful beyond Zalando Tech because it is affected by at least one of the following issues:
- it is dependent on other Zalando projects
- it is difficult or impossible for a non-Zalando to install 
- it has documentation that lacks essential user information, or lacks docs altogether
- it isn’t currently maintained
- it is in pre-MVP (minimum viable product) status
- duplicates the functionality of an existing project and is of questionable quality (due to lack of code review or testing)

**Example projects**: oakkeeper, STUPS, stups2go, solution-center-login, Tarbela, Tranzlate 
**Where it belongs**: [Zalando Incubator](https://github.com/zalando-incubator/)

####Quick Incubator FAQ

#####Why did we make the Incubator?
To support our Open Source First principle, "Share Your Code,” while reserving our main GitHub org for projects useful beyond Zalando.

#####Can you launch a project directly to the Incubator? 
Yes. And you should, if it meets “coding in the open” criteria.

#####Do Incubator projects have to follow our security and compliance guidelines?
Yes, even if we are developing them for Zalandos only, “experimental,” etc.

#####Can an Incubator project ever appear in the main Zalando GitHub org?
Absolutely. Even if Incubator projects aren't currently useful outside of Zalando, we'd like to think that one day they might be.

#####What happens when you transfer a repo from one org to another?
The URL is re-routed to the new organization (zalando-incubator). All git clone, git fetch, or git push operations targeting the previous location will continue to function as if made on the new location. Links will be transferred to the new repository. 

That said, GitHub strongly recommends that anyone who had a reference to the old link locally change to the new URL. Read GitHub’s documentation to learn more.  

#####What happens if I “code in the open” on the main org?
The Guild will ask you to transfer the project yourself to the Incubator, first by filing an Issue on the project and then via HipChat/one-on-one. If we don’t get any response within 14 days, or if you agree to the transfer but don’t take action within a week (seven days), your project will be relocated to the Incubator for you.

#####Is it possible to transfer GitHub issues from one project to the other? 
No, GitHub doesn’t allow it.

#####Is it possible to transfer the ownership of a Github repo to someone else? 
Yes.

###What Makes a Project InnerSource
InnerSource projects meet all the same criteria as “coding in the open” projects, but with one major difference: they appear on GitHub Enterprise, and are not accessible to the public. No one outside of Zalando Tech can see or contribute to them. 

**Wait, I thought we were “Open Source First.” Doesn’t keeping private repos contradict that?**

Nope. Not every project we create will be appropriate for sharing publicly. Some projects will be [too sensitive for publication](https://github.com/zalando/zalando-howto-open-source#never-open-source-these). Other projects would act as “noise,” because they are too tightly coupled to what we do internally. An organization's open source footprint says a lot about that organization, especially if the org cannot maintain a good signal-to-noise ratio.

However, we still want you to share these projects inside Zalando. This is why we advocate the InnerSource collaboration model. 

Put simply, InnerSource operates just like open-source in that project teams invite, accept and reject PRs; provide quality documentation; and build them gradually. The main difference is that InnerSource is limited to a single organization—in our case, Zalando Tech.

With InnerSource, we encourage you to make your GitHub Enterprise organization open to other internal teams so they can find out about your work, fix bugs, make PRs, and even add features that your own team currently has no time to develop. We have internal docs to help your team get started working in this way.

**Where InnerSource projects belong**: GitHub Enterprise
##Open-Source Basics

###Code Review

Ask your team and other peers to:
- review your code
- install and
- test your project **prior to public release**. 

Not sure what to ask for, or how to peer-review? This list of [11 best practices](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/) should help.

###Creating a README

####Do:
- Begin with a short description of what the project is, does, and does not do
- List features
- Place your project in context: who is likely to use it, and why?
- Cover all technical details—installing, running, and configuring—to eliminate friction separating the user from your software
- Address any remaining friction points in separate sections
- Link to additional and more advanced documentation (optional)
- Include a TODO list to invite potential contributors, citing specific needs/bugs/etc.
- Include badges
- If possible, include screenshots and demo videos
- Include a note ("this is in beta") if the project is still in active development

####Don't:
- Refer to Zalando specifics, such as internal teams and processes
- Include large chunks of code without explaining what they represent
- Lack details critical to a user’s ability to install/run/use your project
- Include any code that presents security vulnerabilities

####Syntax and Formatting
Markdown is the simplest and most easily understood syntax; we recommend using it for all your documentation. However, we realize that there are exceptions: PyPi, for example, uses reStructuredText, and the Python community in general doesn’t use Markdown. If Markdown isn’t practical, then we recommend using only one markup format in your project. The format you choose should be [GitHub-supported](https://github.com/github/markup#markups).

For readability, break up text often.

Think about SEO.

###Official Namespace

The official namespace for our projects is ‘**org.zalando**’, where applicable.

###Applying Changes

All repository changes, including those made by maintainers, should come from GitHub pull requests so that we can streamline review and change tracking (as per [GitHub Flow](https://guides.github.com/introduction/flow/)). Everyone should have their own fork, though you can still edit READMEs/documentation/related files with the GitHub “Edit” button. The ‘master’ branch should be the accepted development head; pull requests get merged there.

###Versioning

Version all project artifacts should be [semantically](http://semver.org/). Tag all versions in GitHub with the exact version name (like ‘0.1.0’; do not prefix tags with “v.” or similar). For a better user experience, use the GitHub “release notes” feature to add notes whenever you change something in the new version.

###Maintainers

Maintainers are the contact people for a project. They are also the only contributors who can package new versions and apply changes to the repository (i.e., merge pull requests). Every project must have at least one maintainer. [This helper script](https://github.com/zalando-stups/github-maintainer-cli) gives us an overview of repos that users are maintainers for.

The Open Source Guild reserves the right to contact maintainers to ensure a project remains active/maintained. If the project is not being maintained, we will work with you to either find a new maintainer or remove the project from our organization page. Please be responsive to all internal queries about your project and its status.

####Create a Maintainers File

Every project needs a ‘[MAINTAINERS](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/tree/MAINTAINERS)’ file (listing all maintainers) at its root. Your build/packaging configuration file (e.g., [pom.xml for Maven](https://maven.apache.org/pom.html#Developers)) can fulfill the purpose of a MAINTAINERS file. Format:

     [full name] <email address>
     [second full name] <email address>
     etc.

Our Catwatch application [will collect maintainers from the MAINTAINERS files](https://github.com/zalando/catwatch/issues/29).

####Be Prompt and Responsive

Respond promptly to pull requests and issues. “Within 72 hours” is a good window. Open issues do not make your project “look popular.” Instead, they make it look like you're neglecting your project. If project workload becomes unmanageable, ask the Guild or the community for help.

If you are away/on vacation and can’t respond to PRs/issues promptly, find someone who can.

If you're not going to accept a PR, reject it ASAP and include a brief explanation why.

####Use Issues Creatively
Issues can be good for planning or for onboarding contributors. Issues should include a description of the point, question, discovery, or other detail prompting the issue.

Issues that consist solely of a title appear unprofessional and do not do much to invite discussion from the community.

Label your issues with clear tags. This is a great way to organize and categorize issues.

###Stay Secure
#####Two-Factor Authentication Is Required
GitHub organization members must enable [Two-Factor Authentication (2FA/MFA)](https://help.github.com/articles/about-two-factor-authentication/) in keeping with our Open Source First principle to "Stay Secure." Read [GitHub's post on 2FA](https://help.github.com/articles/about-two-factor-authentication/) for more information.

Don't have a smartphone, and/or want to give your phone number to GitHub? According to GitHub support, SMS or a TOTP app are currently the only primary 2FA methods that work. You can set up 2FA with a Google Voice SMS number, but should add a U2F device as backup.

###About Licensing

####Quick FAQ

#####Which license do we use?
[The MIT license](https://opensource.org/licenses/MIT). MIT is succinct, straightforward, and easy use in closed-source projects. It allows the most broad usage of our source code, and keeps open-sourcing easy and safe.

#####Must I use MIT?
Yes, for all newly created open-source projects.

#####I don't like the MIT license. Can I use another license?

Not without a compelling reason.

#####What if I fork an external project and/or contribute to it?

Keep the original license.

#####I'm open-sourcing a library. What should I do?
Consider using a weak copyleft license that won’t restrict the software that uses it to the same license; will allow usage in closed source software; and will potentially increase the number of users and contributors.

#####What if my team uses an external project whose license is not Zalando-recommended?

You can can use GPL code — but only internally. Be sure it's a version of the GPL that continues to allow for the ASP loophole. AGPL and versions of the GPL with additional restrictions won't work.

#####Who is the license owner?

Zalando SE.

#####Does my project need a LICENSE file?

Yes, at the root of the repository that contains the copy of the selected license (see above). [Here is an example](https://opensource.org/licenses/MIT) for MIT.

#####Do I need to add a license header to every source file?

No. In fact, we discourage it because it blows up file sizes, requires some build checking/pre-processing, and sometimes leads to situations [like this](http://trillian.mit.edu/~jc/humor/ATT_Copyright_true.html). It's also not needed for the licenses we use. Having one `LICENSE` file in the repository is enough.

#####What about a README note?

Yep. Every README{.md,.rst} file must state the following at the end:

>The MIT License (MIT)
>Copyright © [yyyy] Zalando SE, https://tech.zalando.com

>Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

>The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

>THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
>

Replace the [yyyy] field with the year that you created the project, and do not update it. Do not provide multiple years.

#####I still have licensing questions. What can I do?

Ask the Open Source Guild or your delivery lead. See also our TechWiki page (internal doc) for a link to more detailed information.

#####But I am a delivery lead.

Ask your department head.

#####But I am a department head.

Management can work with Legal to determine Intellectual Property concerns.

####Repository of Meta Information

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

####Restrictions Imposed by the License
“Dependency” typically means “being linked with,” “included in your artifact,” or “depends on it during runtime.” Dependencies can limit you. To remain in compliance, check the licenses of your projects. Your build tool’s license does not affect your software’s license. A jar file or Python dependency will affect your software.

#####Unusual Additions

As stated by Zalando Legal, it is OK to use React and other Facebook open-source software projects for Zalando projects.

####There Is No License

If there is no license statement, the author automatically receives a copyright. [This](http://choosealicense.com/no-license/) implies that no one has the right to modify or redistribute the software. If you really need the software, contact the author (who is likely unaware) and ask him/her to provide a proper license.

###Other Repository Information

####JVM Artifacts
Host JVM artifacts (*.jar) on Maven Central in [the ‘org.zalando’ group](https://repo1.maven.org/maven2/org/zalando/). To do this, get a [Sonatype](http://central.sonatype.org/) account. If you don't have an account yet, register with Sonatype using your Zalando email address.

If you want to push to Sonatype but not to *.zalando, register a different Sonatype account with a non-Zalando email address.

####Python Packages
Host Python packages on [PyPI](https://pypi.python.org/pypi/) (PyPI has no namespaces) and make sure that multiple persons have “maintainer” rights.

####SBT plugins
- Publish [on Bintray](https://bintray.com/zalando). An example of the publishing process is [here](http://www.scala-sbt.org/0.13/docs/Bintray-For-Plugins.html).

####Node Modules
[Node](https://www.npmjs.com/) modules [now have namespaces](http://blog.npmjs.org/post/116936804365/solving-npms-hard-problem-naming-packages). Prefix them with a short product name: e.g. [karma](https://karma-runner.github.io/0.12/index.html) plugins are prefixed “karma-”; the same goes for gulp, grunt, etc. Host your Node modules in the public NPM registry. Here is [how to publish to NPM](https://gist.github.com/coolaj86/1318304).

####Docker Images
You can currently browse it [here](https://registry.opensource.zalan.do/ui/), or with the Pier One command line utility. We have an [open source registry](https://registry.opensource.zalan.do/ui/) that everyone can read. It is deployed in the AWS open source account and Docker images can be pushed by any team member to their respective team repo:

```bash
$ # you need to login to registry-write.opensource.zalan.do (workaround for Docker V2 bug)
$ pierone login --url registry-write.opensource.zalan.do
$ docker push registry-write.opensource.zalan.do/myteam/myartifact:1.0
$ # on any other computer:
$ docker pull registry.opensource.zalan.do/myteam/myartifact:1.0 # no auth needed for download!
```

###Working with External Contributors

The Guild supports you in recruiting non-Zalandos to contribute to your project. We simply require that you have external contributors sign a contributor licensing agreement (CLA). A few good models to follow and adapt: [.Net Foundation](https://cla2.dotnetfoundation.org/) example (electronic submission via GitHub account); [Google’s CLA](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#-signing-the-cla) for contributing to AngularJS is a simple click-through form with a Googlebot that automatically checks for signatures; Selenium/Software Freedom Conservancy uses a [Google form](https://docs.google.com/a/zalando.de/forms/d/11Z8LoYpTGUIwCegifVH1YtL9smxVDNk-fOykUZTAWhE/viewform?hl=en_US&formkey=dFFjXzBzM1VwekFlOWFWMjFFRjJMRFE6MQ#gid=0).

###Make Forks Meaningful

*“Forks are for making your own snapshot of a codebase so that you can make a new version of it with your own special sauce, or so that you can contribute a change in the form of a pull request. Simply, you must make a fork whenever you need to modify the codebase, but do not have direct access to do so. New users don’t understand this and end up equating the ‘fork’ button with ‘download’ or ‘bookmark’. Little do they know, you can download code directly from the original repository and you can bookmark things using Github’s stars.”* —[Eric Greer](http://ericgreer.info/github/funny/stupidity/2016/02/28/judging-the-stupidity-of-github-projects.html)

To fork, or not to fork? Some guidelines:
- Only keep the fork open as long as needed.
- “True/Long-Lived forks” are highly discouraged, even from Zalando projects. We avoid internal forks in order to avoid diverging widely from what we have published, and the inevitable hassle of getting the project to a state where we can support both code bases
- Avoid two forks of the same project.

If your goal is to make a small fix to a project, use your own/personal GitHub account.

###Deprecate Responsibly

####How to Deprecate
Add “Deprecated” at the top of your README, as well as a notice stating your plans for the project: deletion, finding a new owner, etc.

After announcing your decision to deprecate the project:
   - notify your users. Put a notice on your README.
   - Wait 60 days.
   - Try to find a new owner. Internal options first, then seek an external owner. Ask the Guild for help.
   - Try to find an external owner. More guidance on this to come soon; for now, alert the Guild of any such plans.

####Tips for Finding a New Owner
Internally, you can use internal mailing lists and HipChat to announce your need. Externally, social media platforms and community boards work well. Add 1-2 sentences to your announcements suggesting how your project might have potential to evolve into something bigger and better.

###Project Promotion

####Catwatch
All Zalando open-source projects are listed on [zalando.github.io](http://zalando.github.io/) (also called [CatWatch](https://github.com/zalando/catwatch)): our own metrics dashboard measuring our most popular public projects and our most active contributors in terms of commits, stars and forks. Please add a [.catwatch.yaml file](https://github.com/zalando/zmon/blob/master/.catwatch.yaml) to the root of your repository to set a human-readable project title and image URL.

####Proactively Communicate
Share your project with:
- relevant LinkedIn Groups
- community forums/boards
- e-newsletters and websites/newsletters dedicated to the problem(s) your project is trying to solve, the relevant languages, etc.
- if you have contacts at a university, pitch your project to their students
- major players in the industry

###Contributing to Non-Zalando Open-Source Projects

####General
We encourage you to contribute to other open-source projects in ways that benefit Zalando — for example, by making bug fixes in Apache, or submitting a patch to a language. Let the Guild know about your external contributions so we can help you get the recognition and support you deserve.

CLAs that are safe: Oracle, Apache.

####Google Projects
For typical CLAs, we are safe — but ask our legal team (guild can provide their contact info) to double-check whenever you’re in doubt.
