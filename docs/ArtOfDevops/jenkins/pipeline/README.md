# Pipeline


# What is Jenkins Pipeline?

Jenkins Pipeline is a suite of plygins which supports implementing and integrating *continuous delivery pipelines* into Jenkins.

A *continous delivery (CD) pipline* is an automated expression of your process for getting software from version control right through to your users and customers.

Pipelines provides an extensible set of tools for modeling simple-to-complex delivery pipelines "as code" via  the Pipeline domain-specific language (DSL) syntax.

Creating a `Jenkinsfile` and commiting it to source provides a number of immediate benefits.
- Automaticallly creates a Pipeline build process for alll branches and pull requests.
- Code review/iteration on the Pipeline (along with the remaining source code).
- Audit trail for the Pipeline.
- Single source of truth for the Pipeline, which can be viewed and edited by multiple members of the project.

### Declarative versus Scripted Pipeline syntax

A `Jenkinsfile` can be written using two types of syntax--Declarative and Scripted.

Declarative and Scripted Pipelines are constructed fundamentally differently. Declarative Pipeline is a more recent feature of Jenkins Pipeline which:

- provide richer syntactical features over Scripted Pipeline syntax, and
- is designed to make writing and reading Pipeline code easier.


### Why Pipeline?

Pipeline adds a powerfull set of automated tools onto Jenkins, supporting use cases that span from simple continous integration to comprehensive CD Pipelines. By modeling a series of related tasks, users can take advantage of many features of Pipeline.

- **Code**: Pipelines are implemented in code typically checked into source control, giving teams the ability to edit, review, and iterate upon their delivery pipeline.
- **Durable**: Pipelines can survive both planned and unplanned restarts of the Jenkins controller.
- **Pausale**: Pipelines can optionally stop and wait for human input or approval before continuing the Pipeline run.
- **Versatile**: Pipelines support complex real-world CD requirements, including the ability to fork/jon, loop, and perform work in parallel.
- **Extensible**: The Pipeline plugin supports custom extensions to its CSL and multiple options for integration with other plugins.


- [Freestyle and Pipeline](freestyle-and-pipeline.md)
- [Pipeline Concepts](concepts.md)