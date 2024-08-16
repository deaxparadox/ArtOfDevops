# Pipeline Syntax Overview


The following Pipeline code skeletons illustrage the fundamental differenes between [Declarative Pipeline Syntax](https://) and [Scripted Pipeline Syntax](https://).

Be aware that both [stage](concepts.md#stage) and [steps](concepts.md#step) are common elements of both Declarative and Scripted Pipeline syntax.


### Declarative Pipeline fundamentals

In Declarative Pipeline syntax, the `pipeline` block defines all the work done throughout your entire Pipeline.

```groovy
pipeline {
    
    /* Execute the Pipeline or any of its stages, on any available agent. */ 
    agent any

    stages {
    
        // Defines the "Build" stage.
        stage('Build') {
            steps {
                // Perform some steps related to the "Build" stage.
                //
            }
        }

        // Defines the "Test" stage.
        stage('Test') {
            steps {
                // 
                // Perform some steps related to the "Test" stage.
                //
            }
        }

        // Defines the "Deploy" stage.
        stage('Deploy') {
            steps {
                // 
                // Perform some steps related to the "Deploy" stage.
                //
            }
        }
    }
}
```


### Scripted Pipeline fundamentals