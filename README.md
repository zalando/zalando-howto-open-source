# OPEN SOURCE RULES AND STRATEGY

**Deprecated document:** this document has been replaced by the documentation on [opensource.zalando.com](https://opensource.zalando.com/docs/releasing/index/) and will not receive further updates - source files for the docs are available in the public [openssource.zalando.com github repository](https://github.com/zalando/zalando.github.io/tree/master/_docs)

----

If you are an Zalando employee please use the [internal version](https://confluence.zalando.net/display/TG/OPEN+SOURCE) because in this public version internal links and contact persons are excluded.

1. [Purpose](#purpose)
2. [Contact](#contact)
3. [Project Publication Process](#Process)
4. [Rules](#rules)
5. [Appendix 1: Philosophy/principles](#A1)
6. [Appendix 2: Potential risks to Zalando’s competitive advantage](#A2)
7. [Appendix 3: How Zalando organizes open source](#A3)
8. [Appendix 4: Zalando’s public GitHub organizations](#A4)
10. [Appendix 5: How to deprecate a project](#A5)
1. [Appendix 6: MIT license](#A6)
1. [Appendix 7: How to honor non-Zalando third-party OSS components](#A7)
1. [Appendix 8: Why you must create a new repo](#A8)

<a name="purpose"></a>
### Purpose 
These open source rules aim to make your OSS efforts more sustainable and successful by reinforcing development habits that improve our software, coding literacy, and craftsmanship. The rules offer guidance and clarify expectations regarding project quality, security, compliance, and usefulness beyond Zalando (see also our OS philosophy/principles in [Appendix 1](#A1)). They also aim to protect Zalando’s competitive advantage (see [Appendix 2](#A2)).
<a name="contact"></a>
### Contact
Please contact Zalando’s Open Source Review Group for open source-related questions and suggestions. For more details on how Zalando organizes open source, see [Appendix 3](#A3).
<a name="Process"></a>
### Project Publication Process 
To publish your project on GitHub.com, please follow these steps:
1. Read all of these rules and make sure your project complies with them.
2. Email the Review Group about your project with the following information:
    + Project name and link:
    + Do you plan to promote your project internally and externally, to build a community of users and contributors?
    + Does this project have any internal Zalando dependencies? (If "Yes," stop here.)
    + Who is your target audience?
    + How many hours per week will you devote to maintaining and growing the project?
    + What does this project solve for potential users, and how is it different (better, faster, simpler) than existing solutions?
    + Did you requested internal feedback?
3. The Review Group will review your project and offer feedback and guidance to support your publication bid.
4. The Review Group might ask you to present your project, but in most cases will request information over email/HipChat.
5. For your project to go live, you must receive the following approvals from the Review Group: security, code quality, documentation, and agreement that the project does not risk our competitive advantage.
6. Upon receiving the Review Group’s approval, you can push your project to the [incubator](https://github.com/zalando-incubator) where it can remain for up to six months. During this time, we expect you to take actions to grow your project. Find more information about Zalando’s public github organizations in [Appendix 4](#A4).
7. If your project grows and evolves, you may ask the Review Group to push your project to [Zalando’s main Open Source organization](https://github.com/zalando). To initiate this process, please contact the Review Group.

<a name="rules"></a>
### Rules 
All open source projects published since 2015 MUST comply to rules 1-9. Non-compliant projects must be deleted from github.com; see [Appendix 5](#A5) for how to deprecate a project. To publish a new project, you MUST also follow rules 10. (If you are an Zalando employee please use the [internal version](https://confluence.zalando.net/display/TG/OPEN+SOURCE) because in this public version internal links and contact persons are excluded. )
1. All projects MUST include an Maintainers.md/rst file listing at least two active maintainers by name and contact email.
2. You MUST create a meaningful README that includes the items requested in Question #11 our application form.
3. You MUST include a [CONTRIBUTING.md/rst guidelines file](https://github.com/nayafia/contributing-template).
4. You MUST create a license file and state that the MIT license applies to all code owned by Zalando. (Please use the license text in [Appendix 6](#A6)). If you use third-party OSS, you MUST only use license-compatible projects/software. You MUST honor the original licenses used in those third-party projects in the license file (see [example](https://github.com/zalando-incubator/zally/blob/master/LICENSE)). For more information and guidance, see [Appendix 7](#A7). Projects published before June 1, 2017 may keep their original license (e.g. Apache 2.0). Contact Legal for personal support on licensing.
5. You SHOULD semantically version project artifacts. You MUST tag all versions in GitHub with the exact version name: e.g., 0.1.0.
6. You SHOULD sign every commit.
7. You MUST create a SECURITY. md file in the main root folder of your repository. This text is sufficient for the file: “If you have discovered a security vulnerability, please email tech-security@zalando.de.”
8. Your repositories MUST NOT, at any time, include Zalando specifics such as credentials and private identifiers.
9. You SHOULD review all merge requests for implanted security backdoors and vulnerable code fragments regardless of who is making the pull request. [User impersonation](http://www.jayhuang.org/blog/pushing-code-to-github-as-linus-torvalds/) is easy.

In addition to the above rules, the following also govern new open source projects you wish to publish on a Zalando-owned GitHub organization.

   10. You MUST create an entirely new Git repository before pushing the project to GitHub. More info in [Appendix 8](#A8).

<a name="A1"></a>
### Appendix 1: Philosophy / Principles 
OSS development is integral to our engineering practices and culture for these reasons:
+ Facilitates skills acquisition (coding, communication, project management, product mindset) that benefits internal and personal development
+ Engages highly skilled external contributors who improve our software quality and relevance
+ Brings about knowledge exchange and innovation through collaborative partnerships with other companies
+ Sends a positive “giving back” massage to a community upon which we rely
+ Implicitly shows developers why working for Zalando will be an enriching and challenging experience, and therefore serves as a highly authentic “employer branding” asset
<a name="A2"></a>
### Appendix 2: Potential Risks to Zalando’s Competitive Advantage 
Anything that risks Zalando’s competitive advantage is not permissible for publication on GitHub.com. This typically means technologies we build that are intrinsic to generating or reinforcing the uniqueness of our customer experience. This could include (but is not limited to):
+ confidential source code
+ recommendation algorithms
+ search functionalities that give us an edge over competitors
We advise you to take a conservative approach and reach out to our Legal team for any ambiguous cases.
<a name="A3"></a>
### Appendix 3: How Zalando organizes open source 
There are two relevant organizations at Zalando: the OSS Review Group and the Open Source Guild. An OS Team is planned but does not exist yet.

OSS Review Group 
+ Purpose
    + Guide Zalando technologists to create high-quality projects that meet our standards.
    + Offer peer review and feedback.
    + Develop policies and processes that reinforce open source development based on quality, end-to-end ownership, broad usefulness to non-Zalandos, and innovation as key values.
+ Responsibility:
    + Meet every two week to approve/reject projects awaiting public release
    + Update and manage the OSS Priority Project List (quarterly)
    + Help Incubator projects graduate to /zalando, the main Zalando organization
    + Manage all Zalando GitHub organizations. The group has the right to remove non-compliant projects from GitHub. (To deprecate a project, see [Appendix 5](#A5).)
+ Membership:
    + VP(s) Engineering
    + Open Source Evangelist (RG leader)
    + 3-5 engineers, delivery leads, and (at least one) dedicated owners
    + Tech Security
    + IT-Compliance
    + Legal
+ Membership Process: Please mail the OSS Review Group if you would like to become a member.

Open Source Guild
Founded in spring 2015, the Guild exists for Zalando technologists to discuss OSS topics and development. Members maintain a lively Google Group that all Zalandos are encouraged to use for these purposes:
+ Announcing new projects and asking for feedback
+ Requesting/offering project demos
+ Knowledge exchange: sharing articles, talks, videos, etc.
+ Generating discussions

Once formed, the OSS Team will offer guidance to structure the Guild into working groups on mentoring, quality, external community building, and documentation.
<a name="A4"></a>
### Appendix 4: Zalando’s Public GitHub organizations 
+ [zalando](https://github.com/zalando): Where we showcase our strongest projects
+ [zalando-incubator](github.com/zalando-incubator): Where we incubate new projects, giving them six months to grow audiences and develop.
+ [zalando-stups](https://github.com/zalando-stups): Setup/purpose in review.
+ [zalando-nakadi](https://github.com/zalando-nakadi): For all repos related to the Nakadi project. Setup/purpose in review.
+ [zalando-zmon](https://github.com/zalando-zmon): For all repos related to the ZMON project. Setup/purpose in review.
+ [zalandoresearch](https://github.com/zalandoresearch): For all repos and code samples generated by Zalando Research. Setup/purpose in review.

<a name="A5"></a>
### Appendix 5: How to deprecate a project
Please follow this process to remove a project from GitHub.com:
1. File a JIRA ticket for your repository deletion process.
2. Archive a version of your repository in your GHE org of choice and follow these steps:
    + You MUST ensure that commit ID’s in the new GHE repo are exactly the same as in the old GitHub repo
    + You MUST register the application in YourTurn/Kio, unless the repo is a library, document, or locally used tool
    + You MUst ensure the SCM URL in YourTurn/Kio is entered correctly (for GHE)
3. Wait for IT-Compliance to approve the request.
4. If your OS project is public on maven, pip, or npm or similar public repositories, please contact Review Group for further instructions.

<a name="A6"></a>
### Appendix 6: MIT License 
Replace the [yyyy] field with the year that you created the project, and do not update it. Do not provide multiple years.

The MIT License (MIT) Copyright © [yyyy] Zalando SE, https://tech.zalando.com

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

<a name="A7"></a>
### Appendix 7: How to honor non-Zalando/third-party OSS components
Copyleft: Copyleft is a legal obligation that Zalando must fulfill when you modify and/or distribute and/or make third party material publicly available (so-called “copyleft trigger”). 

Examples: changing the program code, uploading to public GitHub, sending it to someone else from another company. Copyleft may oblige Zalando to license its modifications also under the license whose copyleft was triggered. In legal terms, “modification” can be interpreted very broadly—e.g. whole libraries or code that you added (so-called “scope of copyleft”).
 
For Modification + Internal and/or Publishing, do not use reciprocal licenses that trigger the copyleft already during internal modification—e.g. RPL or APSL 2.1, AGPLv3.
 
For Modification + Publishing:
+ See above (RPL, ASPL 2.1, AGPLv3, etc.).
+ Do not use licenses with strict copyleft, e.g. GPLv2, GLPLv3, unless you have clearance from Legal.
+ If you use licenses with limited copyleft (e.g. LGPLv2.1, LGPLv3, MPLv2, CPL), please make sure you can fulfill their specific requirements to restrict the copyleft from taking over Zalando’s or other third-party’s code. → reach out to Legal.

License Template for Multi-Licensed Projects without Copyleft

“This {name} Project is in general licensed under the following MIT license except the files named underneath (see corresponding notice files below) 

    (Insert Zalando MIT from Appendix 6 above)

Notice file for (path)/(other file) 

    (Insert license text & copyright notice from the original file here)

Notice file for (path)/(other file) 

    (Insert license text & copyright notice from the original file here)

 (...)

<a name="A8"></a>
### Appendix 8: Why you must create a new repo
“You MUST create an entirely new Git repository before pushing the project to GitHub.”

This rule is a trade-off. On the one hand, we lose information when creating a new git repository. On the other hand, keeping a long history in an existing repository is too-high risk; specifics like credentials could be published by mistake. Security comes first.
