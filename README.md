# joda-to-java-time-bridge

[![Build Status](https://travis-ci.org/airlift/joda-to-java-time-bridge.svg?branch=master)](https://travis-ci.org/airlift/joda-to-java-time-bridge)

Mixed use of Joda-Time and `java.time` results in two different time zone
databases being used at the same time. This inconsistency can lead to
incorrect results. For example, operations as simple as casting a zoned
date time to a Unix time and back will not round-trip.

joda-to-java-time-bridge makes it possible to mix usages of Joda-Time and
`java.time` without the above problem, by changing Joda-Time to delegate
to the time zone database in `java.time` (the one built into the JVM).

It is expected to work with any reasonable version of Joda-Time.
