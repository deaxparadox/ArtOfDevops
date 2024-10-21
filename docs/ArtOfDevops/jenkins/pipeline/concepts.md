# Pipeline Concepts

### Pipeline

A Pipeline is a user-defined models of a CD pipeline. A Pipeline's code defines your entire build process, which typicallly includes stages for building an application, testing it and then delivering it.

Also a `pipeline` block is a `key part of Declarative Pipeline syntax`.

### Node 

A node is machine which is part of the Jenkins environment and is capable of executing a Pipeline.

Also, a `node` block is a `key part of Scripted Pipeline Syntax`.

### Stage

A `stage` block defines a conceptually distinct subset of tasks performed through the entire Pipeline (e.g. "Build", "Test" and "Deploy" stages), which is used by many plugins to visualize or preset Jenkins Pipeline status/progress.


### Step

A single task. Fundamentally, a step tells Jenkins *what* to do at a particular point in time (or "step" in the process). For example, to execute the shell command `make`, use the `sh` step: `sh make`. When a plugin extends the Pipeline DSL, that typically means the plugin has implemented a new *step*.