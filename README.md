# Runtime Tail-Call-Optimization for Java

Applies a simple bytecode-based tail-call-optimization to any java program at
runtime through the use of JVM agents and ASM.

## Build & Run

Build the `agent` target:

```bash
./gradlew ":agent:assemble"
```

Run example application with Gradle...:

```bash
./gradlew ":example:run"
```

...or manually:

```bash
# Running without the agent will trigger a StackOverflow exception
java -javaagent:agent/build/libs/agent.jar \
     -cp example/build/libs/example.jar \
     lab.example.Application
```

## Limitations

Not all cases are covered.
More complex control flows are not recognized as tail-callable.
