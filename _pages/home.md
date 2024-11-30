---
layout: single
permalink: /
author: DaCapo
header:
  image: "assets/images/banner-2560x600.png"
author_profile: false
---

[![github](assets/images/github.png)](https://github.com/dacapobench)

This benchmark suite is intended as a tool for Java benchmarking by the programming language, memory management and computer architecture communities.  It consists of a set of open source, real world applications with non-trivial memory loads.

The initial release of the suite was the culmination of over five years work at eight institutions, as part of the DaCapo research project, which was funded by a National Science Foundation ITR Grant, CCR-0085792.   A further three years of development went into the 2009 release.  The third release took a further fourteen years. That work was been funded by the ANU, the Australian Research Council and a generous donation from Intel.  Since then, development has continued at [ANU with support from Oracle and Google](#currentsponsors).

Our suite evolves to maintain its relevance. It is therefore essential that you **cite the version number** associated with the release in any use of the benchmark, and as a courtesy to the developers, we ask that you **please [cite](cite.txt) the paper** from OOPSLA 2006 describing the suite:

Blackburn, S. M., Garner, R., Hoffman, C., Khan, A. M., McKinley, K. S., Bentzur, R., Diwan, A., Feinberg, D., Frampton, D., Guyer, S. Z., Hirzel, M., Hosking, A., Jump, M., Lee, H., Moss, J. E. B., Phansalkar, A., Stefanovic, D., VanDrunen, T., von Dincklage, D., and Wiedermann, B. **The DaCapo Benchmarks: Java Benchmarking Development and Analysis**, *OOPSLA '06: Proceedings of the 21st annual ACM SIGPLAN conference on Object-Oriented Programing, Systems, Languages, and Applications, (Portland, OR, USA, October 22-26, 2006)* ([pdf](assets/pdf/dacapo-oopsla-2006.pdf), [bibtex](cite.txt)).

# News

* **November 30, 2024**  We are very pleased to announce a maintenance release, [dacapo-23.11-MR1-chopin](https://github.com/dacapobench/dacapobench/releases/tag/v23.11-MR1-chopin).

  The maintenance release includes:
  * Standalone launcher jars in support of AOT systems such as Graal NativeImage.
  * New metrics for request-based workloads.
  * Many additions to the nominal statistics, plus comprehensive statistics added to the release folder, `dacapo-23.11-MR1-chopin/stats`.

  As a maintenance release, we avoid modifying workloads wherever possible. The selection of benchmarks and their versions are *unchanged*. The following bug fixes were made to benchmarks:
  * Incorportate upstream h2 bug [h2database/h2database#4125](https://github.com/h2database/h2database/pull/4125), affecting `h2`, `spring`, `tradebeans`, and `tradesoap` ([#309](https://github.com/dacapobench/dacapobench/pull/309)).
  * Populate database in prepare phase for tradebeans and tradesoap ([#304](https://github.com/dacapobench/dacapobench/pull/304)).
  * Disable logging for YCSB client in `cassandra` ([#272](https://github.com/dacapobench/dacapobench/issues/272)).
  * Reorder key loop nest for `lusearch` ([#264](https://github.com/dacapobench/dacapobench/issues/264)).
  * Fix a race condition in `sunflow` ([#258](https://github.com/dacapobench/dacapobench/issues/258)).

  See the [RELEASE NOTES](https://github.com/dacapobench/dacapobench/blob/47b76675b64711bac22e75fa106fe1c6652b3170/benchmarks/RELEASE_NOTES.md) for more information.

* **November 8, 2023**  14 years since our last major release, we are very pleased to announce [the release of dacapo-23.11-chopin](https://github.com/dacapobench/dacapobench/releases/tag/v23.11-chopin).

  The release includes:
  * New latency metrics, capturing user-experienced tail latencies for eight request-based workloads and jme, a rendering workload.
  * Integrated benchmark characterization metrics which capture defining attributes of each workload.
  * Eight new benchmarks: [biojava](https://biojava.org), [cassandra](http://cassandra.apache.org), [graphchi](https://github.com/GraphChi/graphchi-java), [h2o](https://github.com/h2oai/h2o-3), [jme](http://jmonkeyengine.org), [kafka](https://kafka.apache.org), [spring](https://spring.io/projects/spring-boot) and [zxing](https://github.com/zxing/zxing).
  * A complete overhaul of the trade benchmarks, replacing geronimo with [wildfly](https://wildfly.org).
  * Full updates of all existing benchmarks, bringing them up to date with latest stable versions.


<!--

* **December 1, 2022** Nearly [1500 commits](https://github.com/dacapobench/dacapobench/tree/dev-chopin) after starting on this release, we look forward to making a release candidate in the coming weeks (we are finalizing details of hosting for this much larger release, which at 6GB is too large to be hosted on github).  The release candidates will include:
  * New latency metrics, capturing user-experienced tail latencies for eight request-based workloads and jme, a rendering workload.
  * Integrated benchmark characterization metrics which capture defining attributes of each workload.
  * Eight new benchmarks: [biojava](https://biojava.org), [cassandra](http://cassandra.apache.org), [graphchi](https://github.com/GraphChi/graphchi-java), [h2o](https://github.com/h2oai/h2o-3), [jme](http://jmonkeyengine.org), [kafka](https://kafka.apache.org), [spring](https://spring.io/projects/spring-boot) and [zxing](https://github.com/zxing/zxing).
  * A complete overhaul of the trade benchmarks, replacing geronimo with [wildfly](https://wildfly.org).
  * Full updates of all existing benchmarks, bringing them up to date with latest stable versions.
 As always, you can build the suite from source (using the [dev-chopin branch](https://github.com/dacapobench/dacapobench/tree/dev-chopin)), and we'll soon have release candidates available for download.
-->
<!--
* **June 17, 2019** After two years of work, we have started making evaluation snapshots of our upcoming release [available](https://sourceforge.net/projects/dacapobench/files/evaluation/).
  * Seven diverse and completely new benchmarks: [biojava](https://biojava.org), [cassandra](http://cassandra.apache.org), [graphchi](https://github.com/GraphChi/graphchi-java), [h2o](https://github.com/h2oai/h2o-3), [jme](http://jmonkeyengine.org), [kafka](https://kafka.apache.org), and [zxing](https://github.com/zxing/zxing).
  * A complete overhaul of the trade benchmarks, replacing geronimo with [wildfly](https://wildfly.org).
  * Full updates of all existing benchmarks, bringing them up to date with latest stable versions.
  * A number of benchmarks now have 'huge' configurations that run to GB-sized heaps.

  The suite is not fully calibrated yet, we are yet to cull some of the older benchmarks, and we are still making a number of refinements to the harness and build process.   However, we are looking forward to community feedback on the snapshots of the suite.  We will use the feedback to shape the suite's final composition.   We hope to have the suite ready in Q3 2019.   Please use [github](https://github.com/dacapobench/dacapobench) to file bug reports or contribute fixes or improvements, or share your feedback via  the [mailing list](https://sourceforge.net/p/dacapobench/mailman/).
* **May 10, 2018** An uncalibrated full referesh of every benchmark in the suite is [now available](https://github.com/dacapobench/dacapobench/commit/2baec49bcc9a1dff3acc4e710e00535126166cfd) on github.   This is *not* a release, yet.   Before we release we need to fully calibrate each workload, add new workloads, and assess the whole suite.   We're working on that right now.   In the meantime, we *encourage* you to take a look and give us feedback (on [github](https://github.com/dacapobench/dacapobench/issues), or the [mailing list](https://sourceforge.net/p/dacapobench/mailman/)).
* **Jan 12, 2018** We made a [maintenance release](https://sourceforge.net/projects/dacapobench/files/9.12-bach-MR1/) of the benchmark suite. This is the first full release in a number of years, and fixes a handful of issues with the suite, without changing the existing benchmarks. Major changes are listed [here](https://github.com/dacapobench/dacapobench/blob/master/benchmarks/RELEASE_NOTES.txt). In short, the source distribution should now build correctly (broken URLs fixed), the suite should run fine on Java 8 JVMs (with the exception of tomcat which has an underlying problem [unrelated to DaCapo](https://bugs.openjdk.java.net/browse/JDK-8155588), and we have added a new benchmark, lusearch-fix, which is identical to lusearch except that a one-line [bug fix](https://issues.apache.org/jira/browse/LUCENE-1800) to lucene has been applied (we recommend lusearch-fix over lusearch). The issue with lusearch is described in [this paper](https://dl.acm.org/citation.cfm?id=2048092).
-->
<!--
# Benchmarks

Foo bar 

# Usage
 
Bar bar

# Publications
-->

# Sponsors

## <a name="currentsponsors"></a> Current Sponsors and Contributors

![ANU](assets/images/logos/anu-200x69.jpg)

![Oracle](assets/images/logos/oracle-200x51.png)![Google](assets/images/logos/google-200x68.png)

## <a name="pastsponsors"></a> Past Sponsors and Contributors

![ANU](assets/images/logos/anu-100x35.jpg)
![U Colorado](assets/images/logos/colorado-100x20.png)
![Purdue U.](assets/images/logos/purdue-100x35.png)
![U. Texas](assets/images/logos/texas-100x29.png)
![U. Mass](assets/images/logos/umass-100x40.png)
![UNM](assets/images/logos/unm-100x21.png)

![IBM](assets/images/logos/ibm-100x40.png)
![Intel](assets/images/logos/intel-100x66.png)

![ARC](assets/images/logos/arc-100x61.jpg)![NSF](assets/images/logos/nsf-100x100.png)
