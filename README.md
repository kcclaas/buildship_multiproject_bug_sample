# buildship_multiproject_bug_sample
Sample project to show the problems I'm having with multi-project builds in eclipse.

#### Description
This repo contains three projects, ProjectA, ProjectB, and ProjectC in a similar flat folder structure to our other projects.
ProjectA and ProjectC both depend on ProjectB in a fairly standard multi-project build setup. ProjectB is buildable on its own.

The projects were created in Eclipse. The tasks pane is set to show Project Tasks, but not Task Selectors. When all three projects
are open, the tasks pane includes one copy of both ProjectA and ProjectC, but two copies of ProjectB. One of the copies of ProjectB
will contain runnable tasks, while the other does not. Which one is runnable depends on which project ProjectB considers to be its root.
If I refresh the build of the other Project (A or C), the runnable copy of ProjectB switches.

#### Setup
This is my current setup:  
Mac OS X 10.10.5
Eclipse Oxygen (4.7.0, Eclipse IDE for Java Developers version)  
Buildship 2.1.1.v20170713-0944
Gradle v3.5
