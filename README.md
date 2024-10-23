# exec-provider-example

I want to use [lazy configuration](https://docs.gradle.org/current/userguide/lazy_configuration.html) to run a command-line program which may or may not exist on the system.

My build will take different actions, enable/disable tasks etc. based on this result.

Unfortunately I don't know how to catch the exception being thrown when the provider's `ExecResult` is evaluated.

---

Steps to reproduce:
`$ ./gradlew printFooVersion`

Expected result:
Custom task executes, doesn't find `foo`, so returns a hard-coded default

Actual result:
Uncatchable(?) `java.io.IOException: error=2, No such file or directory`