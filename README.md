# README

This project is a staging ground for hosting experimental changes
to openEMS, with the ultimate goal of submitting them to the upstream.

# Roadmap

*Sometimes an okay answer NOW! is more important than a good answer late.
- [Eric Bogatin](https://www.signalintegrityjournal.com/blogs/4-eric-bogatin-signal-integrity-journal-technical-editor/post/1539-bogatins-20-rules-for-engineers)*

Instead of focusing on finding another great optimization of the FDTD
algorithm or implementation, the current plan is focusing on small and
incremental improvements.

1. Rework Parameter Passing

* Benefits: It provides a solid foundation which is needed in the upcoming
engine, which has many adjustable parameters. As an added bonus, unlike
the current Python module that only accepts hardcoded parameters via
exposed API, but the new code allows passing arbitrary parameters.

* Status: Merge Ready. PR: https://github.com/thliebig/openEMS/pull/140

2. Rework Engine Dispatch

* Benefits: It provides a solid foundation which is needed in the upcoming
engine. Currently, the FDTD extensions use hardcoded switch/case branches
dispatch to devirtualize the main engine, allowing code inlining. But
this creates serious code duplication, making further development extremely
difficult. The proposed patch uses a macro to clean it up.

* Status: Merge Ready. PR: https://github.com/thliebig/openEMS/pull/139

3. Rework CPU detection code.

* Benefits: Remove hardcoded logic in the build system.

* Status: WIP.

4. Rework Multi-Dimensional Array Template

* Benefits: It improves performance by 20% in existing code, without
changing the existing engines. It's also needed by the upcoming engine.

* Status: WIP.

5. First Public Version of Tiling Engine.

* Status: WIP.
