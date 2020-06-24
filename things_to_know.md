# Things to Know About IBM Z and Open Source
IBM Z is similar to, and different from other platforms in many ways.  Open source
software is fundamentally different from traditional z/OS applications in the way
it is developed, packaged, and deployed.  Here are some things to know, depending
on your role:

- [New to the platform](##ibm-z-platform-characteristics), need to know what IBM Z is
- [A veteran mainframer](##open-source-software-characteristics), need to understand open source
  software


## IBM Z Platform Characteristics
The long history of the mainframe often obscures the state-of-the-art features that
continue to be developed for the IBM Z platform.  It's not an overstatement to point
out that many key technologies we take for granted as developers, architects, and
administrators originated on IBM Z.

### IBM Z is a Hardware and Software Family
[IBM Z](https://www.ibm.com/it-infrastructure/z) is a set of hardware models and a collection of operating systems.
Although this platform has been around for a long time, it continues to be a vertically
integrated state-of-the-art compute environment that is the system of record for
much of the world's business transactions.

There are 5 [IBM Z operating systems](https://www.ibm.com/it-infrastructure/z/os) - z/OS, Linux, z/VM, z/VSE, and z/TPF.
Of these, z/OS and Linux are the two operating systems we are focused on here.

z/OS is the traditional mainframe operating system that people tend to think of
when they talk about IBM Z.  It traces its roots back to the first days of the
original s/360 environment, and has gone by the names MVS, and OS/390 prior to z/OS.
This is where the large DB2 databases, and transactional subsystems, like CICS and
IMS live.

Linux on Z is now over 20 years old, and IBM has been deeply involved as a member
of the Linux foundation from the beginning.  The RHEL, SUSE, and Ubuntu distributions
are all supported, and Linux-on-z (LoZ) is a supported platform by several open
source projects.

### IBM Z has a Big Endian Byte Order
IBM Z hardware stores the more significant bytes of a number in higher locations
of the memory occupied by that number.  For example, if you have a 32 bit integer
(4 bytes long), located at address _**a**_, the most significant byte of the number
will be located at _**a+3**_, the second most at _**a+2**_, the third most
at _**a+1**_, and the least significant byte will be at location _**a**_ in memory.
In other words, the least significant byte is at the lowest memory address.

Also referred to as _endianness_, you can read a deeper explanation of byte
ordering [here](https://en.wikipedia.org/wiki/Endianness).

Although other platforms have had big endian architectures in the past, IBM Z is
the lone commercial platform today.  This means that when transferring files
containing binary data to IBM Z running any of the Z operating systems, you have
to be aware that numeric values need to be converted between byte orders.  Some
open source projects, like TensorFlow handle this well, while many do not.  Byte
order mismatch problems can occur when trying to deploy an AI model on an IBM Z
platform that was trained on x/86 hardware.

### z/OS is an EBCDIC Platform
Extended Binary Coded Decimal Interchange Code (EBCDIC) is the default encoding for
z/OS text files.  z/OS has all of the capabilities to properly manage encodings
(often referred to as _internationalization_, or I18N), but many developers don't
think about this.  Open source projects that assume an ASCII environment often
require porting changes on z/OS.

Some environments - like the Java JVM adopted a [UNICODE](https://home.unicode.org/) approach to handling
text strings, and are not affected by ASCII/EBCDIC problems.  The point is to be
aware of this platform characteristic, and know that if some set of code you want
to use on z/OS does not handle text encoding properly, there is work to do.

Also, note that Linux on Z is an ASCII platform, so it does not have this issue.

### z/OS Has a Proprietary Software Management System

### z/OS has a Unix Layer
z/OS is one of the first POSIX-compliant Unix platforms that was certified many years
ago - in the days before Linux existed.  In addition, it has a very old version of
a [Korn shell](http://www.kornshell.org/), and most of the common access interfaces
that people expect - ssh, ftp, telnet, ping, curl, ...  These POSIX interfaces
make up the _Unix System Services_ layer of z/OS (USS).  Unix System Services is
baked into the fabric of z/OS, and is more than just a set of APIs and CLIs.

While the default shell environment is capable for basic operational purposes, it
isn't a modern interface, and doesn't work well as an application development
environment.

There are current open source projects like [zowe](https://github.com/zowe), and
commercial offerings like [IBM Wazi](https://www.ibm.com/products/wazi-for-red-hat-codeready-workspaces) that provide modern infrastructure
for z/OS application development.  It's also a goal of this project to demonstrate
and enable other development technologies on z/OS.  So while USS is a key piece of
infrastructure that supports these environments, you shouldn't look at it as the
primary interface for developing code.

### Linux and z/OS can Share Containers
Linux on Z has always supported container technologies like Docker, and more recently,
[OpenShift](https://developer.ibm.com/components/ibmz/blogs/willie-tejada-redhat-openshift-ibmz/).
With release 2.4, z/OS provides [z/OS container extensions](https://www.ibm.com/support/z-content-solutions/container-extensions/), which creates
a full Docker environment in an address space.  This allows developers to create
container images on either operating system, and deploy on the other.  Such
interoperability across environments gives developers and architects more flexibility
to configure workloads most efficiently.


## Open Source Software Characteristics
Open source software has achieved a level of maturity comparable to the best
proprietary commercial offerings.  The open world today is much less about a specific
project or technology stack, and more about the vast organization of technical talent
across communities, companies, and individuals.  This is where modern standards,
policies, and best practices are born.

### Everything is Integrated and Continuous

### Security is important
