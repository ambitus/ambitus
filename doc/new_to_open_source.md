# Things to Know About Open Source

Many open source projects have achieved a level of maturity comparable to the best proprietary commercial offerings.  The open world today is much less about a specific project or technology stack, and more about the vast organization of technical talent across communities, companies, and individuals.  This is where modern standards, policies, and best practices are born.  A good understanding of open source software is essential for success in today's computing environment.

## Permissive vs Non-Permissive Licenses

This is almost a religious topic in the open source world.  Some believe that all software should be free, and they release their software under terms requiring any embedding or derivative project to require the same terms.  Many argue that these terms have the opposite effect, because they prevent anyone from creating their own license requirements that allow software to be used in commercial environments. The debate has gone on for over 25 years, and won't be resolved any time soon.

At the center of the restrictive license universe is the GNU Public License ([GPL](https://www.gnu.org/licenses/gpl-3.0.en.html)).  It has a number of variants, but they all effectively require that any entity using GPL code, be released as "[free software](https://www.gnu.org/philosophy/free-sw.html)".

Those with commercial software interests have created a set of licenses referred to as "permissive".  These place no restrictions on whether or not one can charge a fee for the rights to use the license.  These licenses allow the source code to be shared under certain terms outlined in the license text.  Common examples of permissive license are [MIT](https://opensource.org/license/MIT), [BSD-3-clause](https://opensource.org/license/bsd-3-clause), and the [Eclipse Public License V2](https://opensource.org/license/epl-2-0), originally created by IBM for the Eclipse foundation.  

There are hundreds of open source licenses in active use today.  A good explanation of permissive vs non-permissive licenses can be found at [OSS Software.org](https://osssoftware.org/blog/open-source-licenses-explained-a-comparison/).

## Everything is Integrated and Continuous

Continuous integration and delivery (CI/CD) are baked in to most open source software projects. The core idea is to enforce project standards by requiring the use of common pipelines and workflows at key points in the development process.  Pipelines may be used to perform static code analysis to look for vulnerabilities, or to build and acceptance-test the code.  These common processes also log important events for review.  These logs can be used to prove compliance with security best practices, which has become increasingly important over the last several years.

CI/CD implies a significant degree of automation, and these frameworks are some of the most common in use:

- [CircleCI](https://circleci.com/)
- [Jenkins](https://www.jenkins.io/)
- [Tekton](https://tekton.dev/)
- [Travis CI](https://tekton.dev/)

In addition to building required processes into the team's standard operations, workflows often include simple repetitive tasks that no one wants to perform by hand.  While each project will have their own set of workflows, most projects in the open source community have gravitated toward a common set of tasks that tend to be automated, so developers share a set of broadly similar development skills.

## Git is the De-facto Source Library System

Git was created by Linux Torvalds and others to manage development of the Linux kernel in 2005 ([https://en.wikipedia.org/wiki/Git](https://en.wikipedia.org/wiki/Git)).  It's a source code manager (SCM) distributed under the terms of the GPL license.  Git repositories can be hosted by anyone, but there are a couple of popular deployments that people often refer to when they mention Git - [github](https://github.com/), and [gitlab](https://gitlab.com/).  The Git SCM itself should not be confused with either of these providers.

Continuous integration workflows are often tightly bound to a project's source code management system. Events registered in the SCM can be used to trigger the start of a workflow to perform some required CI/CD task.  Examples include steps like performing static code analysis on every code check-in, or running a build/test process to be sure the new code will function well enough to pass a minimal test.  These source code managers often have their own pipeline execution infrastructure, and are taking over functions performed by standalone CI/CD frameworks.

## VSCode is the Editor of Choice

The choice of text editor is a personal one for the developer that often generates vigorous debate.  Just within the open source community there are the Unix-based editors, like vi and emacs, and the workstation-based editors of all kinds for Windows and Mac.  Since this is an explanation of the open source environment, we won't get into the merits of host-based editors on z/OS, like the ISPF text editor.

The point to even including this topic in the OSS discussion is to highlight that Microsoft's Virtual Studio Code editor ([vscode](https://code.visualstudio.com/)) has become the editor of choice for a large majority of the open software development community. This is important, because just as Github and Gitlab have become integration points for different parts of the CI/CD pipeline, VSCode is becoming increasingly popular as a means to make best practices the easy path as early in the development cycle as possible - when the code is written.

VSCode has a vast library of plugins that enable live text editing and validation, among many other functions.  Many developers use VSCode as their Git client to manage their source without ever leaving the editor session.  The Zowe project for the mainframe even has the [Zowe Explorer](https://docs.zowe.org/stable/user-guide/ze-install/) extension that helps users develop software directly on z/OS.  The point is, the open source development workflow is built around VSCode and Git, with common workflow components that ensure much better compliance to project standards than could ever be enforced with a simple text editor, and some documented rules.

Choose the text editor you want, but understand that lots of common infrastructure is often built around VSCode.

## Security is Important

Security hasn't always been important in the open source world, but there has been an intense focus on it over the last several years.  The links in the [security section](./README.md#security) of this reference information provide just the starting point for learning more about modern software security.  More often than not, breaches are the result of insufficient IT discipline in individual enterprises rather than a symptom of inadequate industry focus on security.

## Software and Package Management

Open languages are another component of the open source development ecosystem.  As with source code managers and editors, languages themselves are often tightly bound with other parts of the development process.  In particular, many languages have their own associated packaging specification and management capabilities.  Some popular languages with these capabilities include Python, NodeJS, and Rust.  

Mainframe system programmers used to managing software on z/OS in some cases have to adjust their package management strategies.  Open-source-based offerings that run on multiple platforms may follow cross-platform packaging and software management best practices.  They may not follow conventional software management practices for z/OS that include SMP/E.

Open Package management infrastructure is used by developers to handle complex runtime dependencies in their software.  This infrastructure automatically detects and installs all other software that a given package uses.  This is a key characteristic of open source software that has allowed users to share executable code in addition to software in source code form.
