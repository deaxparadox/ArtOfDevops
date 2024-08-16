# Difference between Freestyle and Pipeline

#### Freestyle

Users the Jenkins online console's graphical user interface (UI) to contigure build steps, post-build actions, and configurations. Everything is executed in the agent.

#### Pipeline

Allows users to define build processes using either Groovy-based Scripted Pipeline or Declarative Pipeline. Scripted Pipeline uses a more flexible, script-like syntax, while Declarative Pipeline uses a structured syntax.

Pipeline jobs run on the Jenkins controller, using a lighweight executor to translate pipeline into atomic commands.