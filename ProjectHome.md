
---


---

# Development moved! #

**There is a new development effort at https://github.com/fsaintjacques/disruptor--. Further development will be done there. Old contents of this page follow.**


---


---

.
.
.
.
.
.
.
.
.

**Note: This project is not affiliated with LMAX or the LMAX Disruptor project.**

# Disruptor - Concurrent Programming Framework #

This is a C++ version of the LMAX Disruptor. It is an extremely fast alternative using messaging queues in multithreaded programs. The original framework was written in Java. While one wouldn't expect a C++ port to be significantly faster than the Java version, it is very useful to use in new or existing C++ software.

## Read This First ##

To get a better understanding of what this project is for, see the LMAX Disruptor project documentation at http://code.google.com/p/disruptor/.

## What's the big deal? ##

The disruptor is very fast compared to traditional methods of message passing. Here's a performance chart from the Java LMAX Disruptor:

![http://disruptor.googlecode.com/svn/wiki/images/latency-histogram.png](http://disruptor.googlecode.com/svn/wiki/images/latency-histogram.png)

## How does this differ from the Java version? ##

### Build System ###
The current version include an xcode project and build system. Patches to switch to alternate build systems are welcome.

### Boost ###
While some effort was made to keep the interface similar, one problem is that some design patterns which are standard in Java aren't common (or even supported) in standard C++. Much of this functionality is available from popular Boost C++ library. Some of these features will become mainstream in the upcoming C++0x standard. When they do, most of the boost:: calls can be replaced with std::.

This code also makes use of the excellent boost::atomic, which is not part of the standard boost, but is available from http://www.chaoticmind.net/~hcb/projects/boost.atomic/.

Note that you must link against -lboost\_thread-mt when compiling projects which use the Disruptor.

### Examples ###
For the most part, using the javadoc documentation from the LMAX Disruptor should be fine. There is a simple single-producer/single-consumer example included in the source -- see basicTest.cpp.


### How Can You Help? ###
While the main Disruptor has been ported, particularly the Magic RingBuffer and supporting infrastructure, there are still many unit and performance tests which haven't. Additionally, the code documentation is still targeted towards javadoc, and need to be formatted for doxygen. Patches to address these issues are welcome!
