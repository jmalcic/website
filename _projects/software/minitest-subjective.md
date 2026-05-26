---
title: Minitest Subjective
links:
  - url: https://github.com/jmalcic/minitest-subjective
    type: GitHub repo
    address: jmalcic/minitest-subjective
---

Is your testing [sociable](https://martinfowler.com/bliki/UnitTest.html#SolitaryOrSociable)?
If so, test coverage you collect when running all your tests together will be artifically inflated.
That's because coverage only reflects the fact that _something, somewhere_ touched the covered code,
not necessarily your well-designed test for that specific method, alas.
What would be great is a kind of coverage sensitive to the current test _subject_ as it changes while running tests.

This has been [discussed before](https://www.rubyevents.org/talks/improving-coverage-analysis) by Ryan Davis,
author of Minitest, and you should totally watch his talk to understand why this matters, and why he created
[`minitest-coverage`](https://github.com/minitest/minitest-coverage). That was a while ago, and Ruby now has
more coverage modes (e.g. branch coverage, very useful). This gem takes a different approach to the problem, which also
avoids needing any changes to the coverage API.

The premise is straightforward: where $c_0$ is the coverage after first loading a file (before running any tests),
$c_1$ is the coverage just before running tests _for that file in particular_,
and $c_2$ is the coverage after running the last test for that file,
coverage for that file can be expressed as:
$$c_0 + (c_2 - c_1)$$
This gem just implements addition and subtraction for the different kinds of coverage in coverage results,
plus a basic formatter so you can see the results.
It works with parallel testing, and isn't thread-safe because coverage can't be run per-thread anyway.
