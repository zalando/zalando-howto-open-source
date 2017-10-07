How to Open Source at Zalando
==================

A guide to releasing an open-source project at [Zalando](https://www.zalando.com), Europe's largest online fashion platform. Please feel free to use this as a template for your own organization's open source planning, policymaking, and development efforts. If there's a topic we've missed, or if you have any suggestions for making this better, let us know via our Issues tracker. 

We're really grateful to [Software Lead Weekly](http://softwareleadweekly.com/issues/205), [cron.weekly](https://www.cronweekly.com/issue-51/), [Chris Aniszczyk](https://twitter.com/cra/status/785873124227022848) ([TODO Group](http://todogroup.org/#)), the folks at [Datio Engineering](https://twitter.com/datiobd/status/791942930466344960), [Thomas Lockney](https://twitter.com/tlockney) of Nike, [Jamie Allen](https://twitter.com/jamie_allen) at Starbucks, [Richard Seroter](https://twitter.com/rseroter/status/794197949391785984) at Pivotal, [Peter Zaitsev](https://twitter.com/PeterZaitsev/status/790366161745551360) at Percona, [Jonathan Lipps](https://twitter.com/jlipps/status/793485753896562688) at Sauce Labs, and others for spreading the word about this doc.

Table of Contents
------------------------------------------------------------

  - [Why Open Source?](#why-open-source)
  - [Our Open Source First Principles](#our-open-source-first-principles)
  - [Project Design](#project-design)
    - [What to Ask (and Answer) Before You Open Source](#what-to-ask-and-answer-before-you-open-source) 
    - [Never Open-Source These](#never-open-source-these)
  - [Our Main GitHub Org, The Incubator, and GitHub Enterprise](#our-main-github-org-the-incubator-and-github-enterprise)
    - [The Main Zalando Org and What Makes a Project “Open Source”](#the-main-org-and-what-makes-a-project-open-source)
    - [New Projects: The Incubator](#new-projects-the-incubator)
    - [GitHub Enterprise: For Zalando-Only Repos (InnerSource)](#github-enterprise-for-zalando-only-repos-innersource)
      - [How to InnerSource](#how-to-innersource)
  - [Project Basics](#project-basics)
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
  - [How to Become a Contributor](#how-to-become-a-contributor)
  - [How to Become a Core Contributor](#how-to-become-a-core-contributor)
  - [Google Projects](#google-projects)

### Why Open Source?

Because it can: improve quality, mitigate risk, increase trust, save us money, expand our technology choices, be fun, enable us to give back to the community, strengthen our tech brand, and attract talent.

### Our Open Source First Principles

**Vision**: 
*We strongly believe that open source software benefits the tech community, and that providing broadly useful code to the world is a virtue. We strive to work in an open source way to the betterment of Zalando and the world.*

- **Do “Open Source First”**: If your Zalando project can also be useful to non-Zalandos, consider releasing it as open source and ask for guidance.
- **Take Ownership**: Your team is responsible for ensuring that it’s possible to open-source your project. Your delivery lead is available for guidance.
- **Be Safe**: To ensure the broadest possible use of your project, use the MIT License only.
- **Deliver Quality**: Provide a great out-of-the-box experience.
- **Provide Documentation**: Include a clear README and default working configuration.
- **Stay Secure**: Make sure your project doesn’t include Zalando specifics, such as credentials and private identifiers.
- **Ask for Help**: Find colleagues to brainstorm ideas for your project and to review your work.
- **Promote**: Tell the world about your project via blog posts, social media and conference talks.
- **Join the Open Source Guild**: Help us make open source stronger at Zalando! Come on, it'll be fun. :)

[This blog post](https://tech.zalando.com/blog/zalando-techs-new-open-source-principles/) might also be of interest.

### Project Design

#### What to Ask (and Answer) Before You Open Source
[Danese Cooper](https://twitter.com/DivaDanese) and [Duane O'Brien](https://twitter.com/DuaneOBrien) at PayPal have [shared a succinct four-question approach](https://opensource.com/business/16/1/4-questions-ask-open-sourcing-project) that has influenced our own:

- Who cares?
- Are we still using it?
- Are we committed to it?
- Can it be developed in one public tree?

To encourage our engineers to dive deeper on the first point, we've created [this product template/checklist](https://github.com/zalando/zalando-howto-open-source/blob/master/producttemplate.md). It's meant to raise the key questions necessary for a project to reflect a strong "product mindset" and maximum project utility for the community at large.

#### Never open-source these:
- PCI DSS-related projects: e.g. payment services
- Zalando-specific projects: things tightly coupled to/dependent upon our systems
- Projects you don't plan to maintain and grow a community around
- Domain knowledge
- Customer data
- Unique Selling Points (USPs)
- Anything that would risk our competitive advantage. This typically means technologies we build that are intrinsic to generating or reinforcing the uniqueness of our customer experience, and that—if made public—would enable our competitors to implement it and erase our uniqueness. This could be:
  - confidential source code
  - recommendation algorithms
  - search functionalities that give us an edge over competitors

If you're open-sourcing a project that has contained sensitive information in the past, the sensitive information can still be retrieved from the Git commit history. Create an entirely new Git repo for it before pushing it to GitHub.

No issues? Great! On to the next section ...

### Our Main GitHub Org, The Incubator, and GitHub Enterprise

Based on quality, usefulness and maintenance considerations, we use this matrix to decide how to classify and place our projects:

- InnerSource = GitHub Enterprise
- Newly launched projects that meet our criteria for open source = Incubator
- Open source = main Zalando org

In the inverse, you could think of these three categories as “steps” for your project as it develops from an idea to a minimum viable product (MVP) that someone on the outside could understand, use and possibly work on as a contributor. 

The next sections offer more details on differences between open source, “coding in the open” and InnerSource.

#### The Main Org and What Makes a Project “Open Source”

Zalando's main GitHub organization is [/zalando](https://github.com/zalando). This organization is reserved for projects meeting these criteria:
- **is useful beyond Zalando**. It is free of Zalando dependencies and simple for a non-Zalando to install and start using.
- **has user-friendly documentation** that is up-to-date and clear about what the project does, and how to install/start/configure/run it. ([This template can help you](https://github.com/zalando/zalando-howto-open-source/blob/master/READMEtemplate.md).)
- **is tested**. It has automated tests and takes advantage of test coverage.
- **is under active development**, or is stable enough to be considered a “finished” product. If the project is incomplete, at least one maintainer has worked on it in the last three months. If it’s stable and doesn’t require constant maintenance, you’ve stated as much in your README.
- **is innovative**. If it duplicates an existing project, it does at least one thing better, faster, differently, etc., or is higher-quality.
- **meets our non-negotiable guidelines** regarding security and compliance. You need to include a LICENSE.md, for example.
- **is an MVP**. It either meets or surpasses “minimum viable product” status. An outside developer could use it and even contribute to it. If it’s buggy or very early-stage, it includes a brief development status in the intro stating as much. (This template can help you.)
- ** has a CONTRIBUTING.md.** For a template, [go here](https://github.com/nayafia/contributing-template).
- **has a plan**. Its maintainers care about making it a success. They commit to responding to PRs and issues in a timely manner (48-72 hours), thank contributors, and convert quality contributors to trusted maintainers as appropriate. If you need some guidance, check out [Mozilla's helpful resources](https://mozilla.github.io/open-leadership-training-series/articles/open-project-maintenance/open-project-maintenance/) on this topic.

- **Example projects**: [Patroni](https://github.com/zalando/Patroni), [Connexion](https://github.com/zalando/connexion), [Zappr](https://github.com/zalando/zappr), [Python NSEnter](https://github.com/zalando/python-nsenter), [Tailor](https://github.com/zalando/tailor), [Grafter](https://github.com/zalando/grafter), [SwiftMonkey](https://github.com/zalando/swiftmonkey).

We have also published some document-only repositories like this one, our RESTful API guidelines, and the Tech Radar. These reflect our organizational perspective on technical topics, and are therefore of potential interest to other companies who are looking for ideas and case studies. We should keep them limited in number and broad in scope.

#### New Projects: The Incubator

[The Incubator](https://github.com/zalando-incubator) is where your Zalando project will first appear in public. It is a proving ground for brand-new projects that meet all the above criteria. It is where we can experiment and publish projects that show clear promise of being useful to others because they are A) out-of-the-box usable to non-Zalandos and B) highlight a compelling technical challenge that we are solving with software.

Projects that demonstrate in the Incubator can be transferred to our main organization, /zalando. 

###### What happens when you transfer a repo from one org to another?
The URL is re-routed to the new organization (zalando-incubator). All git clone, git fetch, or git push operations targeting the previous location will continue to function as if made on the new location. Links will be transferred to the new repository. 

That said, GitHub strongly recommends that anyone who had a reference to the old link locally change to the new URL. [Read GitHub’s documentation](https://help.github.com/articles/transferring-a-repository/#redirects-and-git-remotes) to learn more.

###### What happens if I release a project directly to /zalando?
You will be asked to transfer the project yourself to the Incubator. If we don’t get any response within three days, or if you agree to the transfer but don’t take action within three days, your project will be relocated to the Incubator for you.

###### Is it possible to transfer GitHub issues from one project to the other? 
No, GitHub doesn’t allow it. (There are migration tools that can copy issues and their comments to another project, but these don't transfer the relevant author info; they assign ownership to the account used by the migration tool.)

###### Is it possible to transfer the ownership of a Github repo to someone else? 
Yes.

#### GitHub Enterprise: For Zalando-Only Repos (InnerSource)
InnerSource projects are the repositories we use internally at Zalando. They appear on GitHub Enterprise, and are not accessible to the public. No one outside of Zalando Tech can see or contribute to them. 

**Wait, I thought we were “Open Source First.” Doesn’t keeping repos on GHE contradict that?**

Nope. Not every project we create is appropriate for sharing publicly. Some projects will be [too sensitive for publication](https://github.com/zalando/zalando-howto-open-source#never-open-source-these). Other projects would act as “noise,” because they are too tightly coupled to what we do internally. An organization's open source footprint says a lot about that organization, especially if the org cannot maintain a good signal-to-noise ratio.

However, we still want you to share these projects inside Zalando, on GHE. This is why we advocate the InnerSource collaboration model. InnerSource operates just like open-source in that project teams invite, accept and reject PRs; provide quality documentation; and build them gradually. The main difference is that InnerSource is limited to Zalando Tech. Make your GHE organization open to other internal teams so they can find out about your work, fix bugs, make PRs, and even add features that your own team currently has no time to develop. 

We request that you use private GHE repositories only if they include sensitive information that can't store elsewhere.

**Where InnerSource projects belong**: GitHub Enterprise

##### How to InnerSource
[Here's our homegrown how-to](https://github.com/zalando/zalando-howto-open-source/blob/master/innersource.md) with materials to get you started.

## Project Basics

### Code Review

Ask your team and other peers to:
- review your code
- install and
- test your project prior to public release. 

Not sure what to ask for, or how to peer-review? This list of [11 best practices](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/) should help.

### Creating a README

#### Do:
- [Use this checklist](https://github.com/zalando/zalando-howto-open-source/blob/master/READMEtemplate.md). 
- Break up text often, for better readability.
- Think about SEO.

#### Don't:
- Refer to Zalando specifics, such as internal teams and processes
- Include large chunks of code without explaining what they represent
- Include any code that presents security vulnerabilities

#### Syntax and Formatting
Markdown is the simplest and most easily understood syntax; we recommend using it for all your documentation. However, we realize that there are exceptions: PyPi, for example, uses reStructuredText, and the Python community in general doesn’t use Markdown. If Markdown isn’t practical, then we recommend using only one [GitHub-supported](https://github.com/github/markup#markups) markup format.

### Official Namespace

The official namespace for our projects is ‘**org.zalando**’, where applicable.

### Applying Changes

All repository changes, including those made by maintainers, should come from GitHub pull requests so that we can streamline review and change tracking (as per [GitHub Flow](https://guides.github.com/introduction/flow/)). Everyone should have their own fork, though you can still edit READMEs/documentation/related files with the GitHub “Edit” button. The ‘master’ branch should be the accepted development head; pull requests get merged there.

### Versioning

Version all project artifacts should be [semantically](http://semver.org/). Tag all versions in GitHub with the exact version name (like ‘0.1.0’; do not prefix tags with “v.” or similar). For a better user experience, use the GitHub “release notes” feature to add notes whenever you change something in the new version.

### Maintainers

Maintainers are the contact people for a project. They are also the only contributors who can package new versions and apply changes to the repository (i.e., merge pull requests). Every project must have at least one maintainer. [This helper script](https://github.com/zalando-stups/github-maintainer-cli) gives us an overview of repos that users are maintainers for.

The Open Source Guild reserves the right to contact maintainers to ensure a project remains active/maintained. If the project is not being maintained, we will work with you to either find a new maintainer or remove the project from our organization page. Please be responsive to all internal queries about your project and its status.

#### Create a Maintainers File

Every project needs a ‘[MAINTAINERS](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/tree/MAINTAINERS)’ file (listing all maintainers) at its root. Your build/packaging configuration file (e.g., [pom.xml for Maven](https://maven.apache.org/pom.html#Developers)) can fulfill the purpose of a MAINTAINERS file. Format:

     [full name] <email address>
     [second full name] <email address>
     etc.

Our Catwatch application [collects maintainers from the MAINTAINERS files](https://github.com/zalando/catwatch/issues/29).

#### Be Prompt and Responsive

Respond promptly to pull requests and issues. “Within 72 hours” is a good window. Open issues do not make your project “look popular.” Instead, they make it look like you're neglecting your project. If project workload becomes unmanageable, ask the Guild or the community for help.

If you are away/on vacation and can’t respond to PRs/issues promptly, find someone who can.

If you're not going to accept a PR, reject it ASAP and include a brief explanation why.

If you're feeling maintainer burnout or facing some trolling behavior, give Jon Schinklert's [Maintainers Guide to Staying Positive](https://github.com/jonschlinkert/maintainers-guide-to-staying-positive) a read; it might help you to feel better.

#### Use Issues Creatively
Issues can be good for planning or for onboarding contributors. Issues should include a description of the point, question, discovery, or other detail prompting the issue.

Issues that consist solely of a title appear unprofessional and do not do much to invite discussion from the community.

Label your issues with clear tags. This is a great way to organize and categorize issues.

#### Provide a Pull-Request Template

The Issues Tracker is the entry point for onboarding contributors, so use our [pull request template](pull_request_template.md) to create a roadmap for your project or to track bugs. A pull request template improves development quality and provides a common guideline for contributors to follow. It also enables to you to reference issues and shows others your development progress.

Add a `PULL_REQUEST_TEMPLATE.md` into the root of your project folder. Once you merge it, every new pull request will use this template. [GitHub's help section](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/) offers a step-by-step guide with more information about PR templates.

### Stay Secure
##### Two-Factor Authentication Is Required
GitHub organization members must enable [Two-Factor Authentication (2FA/MFA)](https://help.github.com/articles/about-two-factor-authentication/) in keeping with our Open Source First principle to "Stay Secure." Read [GitHub's post on 2FA](https://help.github.com/articles/about-two-factor-authentication/) for more information.

Don't have a smartphone, and/or want to give your phone number to GitHub? According to GitHub support, SMS or a TOTP app are currently the only primary 2FA methods that work. There are mobile and desktop TOTP apps that also work. See [GitHub's article on 2FA via TOTP apps](https://help.github.com/articles/configuring-two-factor-authentication-via-a-totp-mobile-app/) for more information. You can set up 2FA with a Google Voice SMS number, but should add a U2F device as backup.

### About Licensing

#### Quick FAQ

##### Which license do we use?
[The MIT license](https://opensource.org/licenses/MIT). MIT is succinct, straightforward, and easy use in closed-source projects. It allows the most broad usage of our source code, and keeps open-sourcing easy and safe. You must include a separate license file in your repository with the entire text of the MIT license included. 

If your project uses the MIT license and incorporates third-party OSS components, then you must attach this sentence in your license file: “This software is licensed under the MIT license (see below), unless otherwise stated in the license files in higher directories (if any)." Please also provide the license files for every third-party source you add.

[This helpful blog post](https://writing.kemitchell.com/2016/09/21/MIT-License-Line-by-Line.html) breaks down the license line by line for you. (If you're really interested in open source licensing, check out [Rosenlaw & Einschlag's free online book](http://www.rosenlaw.com/oslbook.htm) and/or [O'Reilly's/Andrew M. St. Laurent's](http://www.oreilly.com/openbook/osfreesoft/book/). These are a little dated, but still useful.)

For documents like this how-to, we recommend using [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).

##### Must I use MIT?
Yes, for all newly created open-source projects.

##### I don't like the MIT license. Can I use another license?

Not without a compelling reason.

##### What if I fork an external project and/or contribute to it?

Keep the original license.

##### I'm open-sourcing a library. What should I do?
Consider using a weak copyleft license that won’t restrict the software that uses it to the same license; will allow usage in closed source software; and will potentially increase the number of users and contributors.

##### What if my team uses an external project whose license is not Zalando-recommended?

You can can use GPL code — but only internally. Be sure it's a version of the GPL that continues to allow for the ASP loophole. AGPL and versions of the GPL with additional restrictions won't work.

##### Who is the license owner?

Zalando SE.

##### Does my project need a LICENSE file?

Yes, at the root of the repository that contains the copy of the selected license (see above). [Here is an example](https://opensource.org/licenses/MIT) for MIT.

##### Do I need to add a license header to every source file?

No. In fact, we discourage it because it blows up file sizes, requires some build checking/pre-processing, and sometimes leads to situations [like this](http://trillian.mit.edu/~jc/humor/ATT_Copyright_true.html). It's also not needed for the licenses we use. Having one `LICENSE` file in the repository is enough.

##### What about a README note?

Yep. Every README{.md,.rst} file must state the following at the end:

>The MIT License (MIT)
>Copyright © [yyyy] Zalando SE, https://tech.zalando.com

>Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

>The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

>THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
>

Replace the [yyyy] field with the year that you created the project, and do not update it. Do not provide multiple years.

##### I still have licensing questions. What can I do?

Ask the Open Source Guild or your delivery lead. See also our TechWiki page (internal doc) for a link to more detailed information.

##### But I am a delivery lead.

Ask your department head.

##### But I am a delivery head.

Management can work with Legal to determine Intellectual Property concerns.

#### Repository of Meta Information

Many package managers include a feature to make the applied license machine readable. Use these! An example for [Maven](https://maven.apache.org/pom.html#Licenses):

```xml
<licenses>
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

#### Restrictions Imposed by the License
“Dependency” typically means “being linked with,” “included in your artifact,” or “depends on it during runtime.” Dependencies can limit you. To remain in compliance, check the licenses of your projects. Your build tool’s license does not affect your software’s license. A jar file or Python dependency will affect your software.

##### Unusual Additions

As stated by Zalando Legal, it is OK to use React and other Facebook open-source software projects for Zalando projects.

#### There Is No License

If there is no license statement, the author automatically receives a copyright. [This](http://choosealicense.com/no-license/) implies that no one has the right to modify or redistribute the software. If you really need the software, contact the author (who is likely unaware) and ask him/her to provide a proper license.

### Other Repository Information

#### JVM Artifacts
Host JVM artifacts (*.jar) on Maven Central in [the ‘org.zalando’ group](https://repo1.maven.org/maven2/org/zalando/). To do this, get a [Sonatype](http://central.sonatype.org/) account. If you don't have an account yet, register with Sonatype using your Zalando email address.

If you want to push to Sonatype but not to *.zalando, register a different Sonatype account with a non-Zalando email address.

#### Python Packages
Host Python packages on [PyPI](https://pypi.python.org/pypi/) (PyPI has no namespaces) and make sure that multiple persons have “maintainer” rights.

#### SBT plugins
- Publish [on Bintray](https://bintray.com/zalando). An example of the publishing process is [here](http://www.scala-sbt.org/0.13/docs/Bintray-For-Plugins.html).

#### Node Modules
[Node](https://www.npmjs.com/) modules [now have namespaces](http://blog.npmjs.org/post/116936804365/solving-npms-hard-problem-naming-packages). Prefix them with a short product name: e.g. [karma](https://karma-runner.github.io/0.12/index.html) plugins are prefixed “karma-”; the same goes for gulp, grunt, etc. Host your Node modules in the public NPM registry. Here is [how to publish to NPM](https://gist.github.com/coolaj86/1318304).

#### Docker Images
You can currently browse it [here](https://registry.opensource.zalan.do/ui/), or with the Pier One command line utility. We have an [open source registry](https://registry.opensource.zalan.do/ui/) that everyone can read. It is deployed in the AWS open source account and Docker images can be pushed by any team member to their respective team repo:

```bash
$ # you need to login to registry-write.opensource.zalan.do (workaround for Docker V2 bug)
$ pierone login --url registry-write.opensource.zalan.do
$ docker push registry-write.opensource.zalan.do/myteam/myartifact:1.0
$ # on any other computer:
$ docker pull registry.opensource.zalan.do/myteam/myartifact:1.0 # no auth needed for download!
```

### Working with External Contributors

The Guild enthusiastically supports you in recruiting non-Zalandos to contribute to your project. Collaboration and community are part of the fun of open source. 

Give GitHub's ["Creating a new contributor on-ramp" doc](https://github.com/blog/2128-creating-a-new-contributor-on-ramp) a look for some expert guidance. (TL;DR version = be welcoming, inclusive, and clear about what sorts of contributions you're looking for most).

Please ask external contributors to sign a contributor licensing agreement (CLA). A few good models to follow and adapt: [.Net Foundation](https://cla2.dotnetfoundation.org/) example (electronic submission via GitHub account); [Google’s CLA](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#-signing-the-cla) for contributing to AngularJS is a simple click-through form with a Googlebot that automatically checks for signatures; Selenium/Software Freedom Conservancy uses a [Google form](https://docs.google.com/a/zalando.de/forms/d/11Z8LoYpTGUIwCegifVH1YtL9smxVDNk-fOykUZTAWhE/viewform?hl=en_US&formkey=dFFjXzBzM1VwekFlOWFWMjFFRjJMRFE6MQ#gid=0).

### Make Forks Meaningful

*“Forks are for making your own snapshot of a codebase so that you can make a new version of it with your own special sauce, or so that you can contribute a change in the form of a pull request. Simply, you must make a fork whenever you need to modify the codebase, but do not have direct access to do so. New users don’t understand this and end up equating the ‘fork’ button with ‘download’ or ‘bookmark’. Little do they know, you can download code directly from the original repository and you can bookmark things using Github’s stars.”* —[Eric Greer](http://ericgreer.info/github/funny/stupidity/2016/02/28/judging-the-stupidity-of-github-projects.html)

To fork, or not to fork? Some guidelines:
- Only keep the fork open as long as needed.
- “True/Long-Lived forks” are highly discouraged, even from Zalando projects. We avoid internal forks in order to avoid diverging widely from what we have published, and the inevitable hassle of getting the project to a state where we can support both code bases
- Avoid two forks of the same project.

If your goal is to make a small fix to a project, use your own/personal GitHub account.

### Deprecate Responsibly

#### How to Deprecate
Add “Deprecated” at the top of your README, as well as a notice stating your plans for the project: deletion, finding a new owner, etc.

After announcing your decision to deprecate the project:
   - notify your users. Put a notice on your README.
   - Wait 60 days.
   - Try to find a new owner. Internal options first, then seek an external owner. Ask the Guild for help.
   - Try to find an external owner. More guidance on this to come soon; for now, alert the Guild of any such plans.

#### Tips for Finding a New Owner
Internally, you can use internal mailing lists and HipChat to announce your need. Externally, social media platforms and community boards work well. Add 1-2 sentences to your announcements suggesting how your project might have potential to evolve into something bigger and better.

### Project Promotion

#### zalando.github.io: Our Open-Source Projects Dashboard
All Zalando open-source projects are listed on [zalando.github.io](http://zalando.github.io/) (also called [CatWatch](https://github.com/zalando/catwatch)): our own metrics dashboard measuring our most popular public projects and our most active contributors in terms of commits, stars and forks. Please add a [.catwatch.yaml file](https://github.com/zalando/zmon/blob/master/.catwatch.yaml) to the root of your repository to set a human-readable project title and image URL.

#### Proactively Communicate
Share your project with:
- relevant LinkedIn Groups
- community forums/boards
- e-newsletters and websites/newsletters dedicated to the problem(s) your project is trying to solve, the relevant languages, etc.
- if you have contacts at a university, pitch your project to their students
- major players in the industry

### Contributing to Non-Zalando Open-Source Projects

We encourage you to contribute to other open-source projects in ways that benefit Zalando. Some ways you might contribute:

— making bug fixes in Apache
- making bug fixes to projects you're using on the job
- submitting a patch or change to a language (for example, [Clojure](http://clojure.org/community/contributing))
- pitching a feature request that your team/dept needs to a project we're using, getting confirmation from the maintainers to go forward, and doing the work
  - a good idea is to review the project's GitHub Issues Tracker to see if anyone else has made the same feature request; restart that conversation and see if you can get them + others to work collaboratively to make the needed change 

#### How to Become a Contributor

Before writing a line of code to change a project, we highly recommend reaching out to the project maintainers via the Issues Tracker and letting them know about your plans (many projects already require this as a first step). There might already be an issue filed that matches your needs, and/or someone working on the changes you're recommending. You don't ever want to invest a lot of time and work into making a change, only to have the project maintainers reject it as out of scope. This will frustrate you, and it will frustrate them.

These articles from others in the community provide more detailed advice for getting started:

- [How to Become an Amazing Contributor](https://opensource.com/life/11/3/how-become-amazing-contributor-open-source-project) by Daniel Doubrovkine for opensource.com/RedHat
- [How to Contribute to Open Source Projects](http://www.drdobbs.com/open-source/how-to-contribute-to-open-source-project/231000080) by Brian Behlendorf for Dr. Dobb's
- [The Eight Essential Traits of a Great Open Source Contributor](https://blog.newrelic.com/2014/10/21/open-source-contributors/) by Ander Lester/New Relic
- [14 Ways to Contribute to Open Source Without Being a Programming Genius or a Rock Star](http://blog.smartbear.com/programming/14-ways-to-contribute-to-open-source-without-being-a-programming-genius-or-a-rock-star/) also by Andy Lester, this time for SmartBear

#### How to Become a Core Contributor

Ah, so you want to get more serious about contributing! Excellent. Becoming a core contributor to a major project is a fantastic way to learn from others, grow your network and keep the open source infrastructure we depend on strong and reliable. Others in the general open source community have written great how-to's on this topic. Here are a few:

- [Tips for Becoming a Core Contributor](https://www.wordfugue.com/tips-becoming-core-contributor/) by Philip James 
- [On Becoming a Core Contributor](http://glasnt.com/blog/2016/06/08/on-becoming-a-core-contributor.html) by Katie McLaughlin
- [Apache Software Foundation's how-to](https://community.apache.org/contributors/), including "Moving From Contributor to Committer," [FAQ](https://www.apache.org/dev/committers.html) and [guide](https://www.apache.org/dev/new-committers-guide.html)

Please let the Guild know about your external contributions so we can help you get the recognition and support you deserve.

##### CLAs 

For typical CLAs, we are safe — but ask our legal team (guild can provide their contact info) to double-check whenever you’re in doubt. CLAs that are safe: Oracle, Apache, Google Projects.
