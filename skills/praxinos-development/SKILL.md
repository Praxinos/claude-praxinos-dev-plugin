---
name: "praxinos-development"
description: Apply when creating or editing Unreal Engine 5 project, plugin, or engine code. Follow Epic's coding standard, compile the affected target, and add and run integration tests for changed behavior.
---

# Praxinos Development Skill

Apply this workflow to UE5 code edits, including C++, C# build tooling, and code used by Unreal plugins. Use the project's UE version and existing conventions. Keep the work scoped to the user's requested change. Do not use the `auto` keyword in code you create or modify. Write documentation directly in the code as Doxygen comments; do not create or update documentation in any other form.

When a function would evaluate the same accessor, lookup, or cast more than once to reach the same data (in successive statements, or in a loop condition or body), store the result once in a local variable, using a reference for containers, and reuse it. Keep separate calls when the result can differ between evaluations: different arguments, data that depends on the loop iteration, or data modified in between.

Organize members in classes and structs in this order:

1. Destructor and constructor
2. Public static methods
3. Public non-static methods
4. Private methods
5. Public attributes
6. Private attributes

Organize #include directives in this order:

1. The .cpp file's associated header
2. Unreal headers
3. Odyssey headers

1. Inspect the affected module, its build configuration, nearby tests, and the engine version. Check the [Epic C++ Coding Standard](https://dev.epicgames.com/documentation/en-us/unreal-engine/epic-cplusplus-coding-standard-for-unreal-engine), using the version matching the project when available. Follow it for new and modified code; reconcile local conventions without introducing unrelated formatting changes. Check naming, prefixes, header organization, `UCLASS`/`USTRUCT`/`UPROPERTY` usage, includes, braces, indentation, and comments as applicable.
2. Add or update an automated integration test for each behavior changed by the code. Exercise the interaction between the affected UE components or systems, including a failure or boundary path when relevant. Use the project's established test framework; otherwise choose an appropriate UE Automation, Functional, or feature test. A test that only duplicates a helper's implementation does not satisfy this requirement. Make the test discoverable and independent of prior Editor or game state, and clean up resources it creates. For a purely mechanical change with no behavior to test, say why an integration test cannot meaningfully be added.
3. Compile the affected Editor, game, plugin, or other relevant target using the project's actual engine installation and build configuration. Include the new test code in the build. Resolve compile errors introduced by the change and recompile. Do not treat static inspection, IDE diagnostics, or Live Coding as a completed build.
4. Run the relevant integration test and inspect the actual result and logs. Fix failures caused by the change and rerun the affected build and test. If the build or test cannot run because the required engine, platform, assets, permissions, or environment are unavailable, record the attempted command, the concrete blocker, and the unverified work; never report success without execution.
5. In the final report, state the code and test changed, the build target and result, and the integration test name and result. Include remaining failures or blockers precisely.

Reference: [Epic's Automation Test Framework](https://dev.epicgames.com/documentation/en-us/unreal-engine/automation-test-framework-in-unreal-engine) and [running automation tests](https://dev.epicgames.com/documentation/unreal-engine/run-automation-tests-in-unreal-engine).
