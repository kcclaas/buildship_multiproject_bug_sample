# buildship_multiproject_bug_sample
Sample project to show the problems I'm having with multi-project builds in eclipse.

#### Description
This repo contains two projects, ProjectA and ProjectB in a similar flat folder structure to our other projects.
ProjectA depends on ProjectB in a fairly standard multi-project build setup.

The projects were created in Eclipse. Once the depency between ProjectA and B was created within the build/settings scripts,
and the builds and gradle tasks pane were refreshed, I was no longer able to run tasks in ProjectB from the gradle tasks pane.
The same happens after I close the projects, delete them from Eclipse, and reimport ProjectA.

When in this state, tasks in the subproject show a green gear next to them, the same as in the root project. However, double-clicking
a task in the subproject does not run the task, and right-clicking it displays a "Cannot run tasks for included builds" message
instead of "Run Gradle Tasks".

If default tasks are set within the build script, they will still run when I double-click the project in the gradle tasks pane.
It is also possible to create run configurations to run the tasks on the subproject, and to run tasks from ProjectB on the
command line.

#### Setup
This is my current setup:  
Mac OS X 10.10.5
Eclipse Oxygen (4.7.0, Eclipse IDE for Java Developers version)  
Buildship 2.1.1.v20170713-0944
Gradle v3.5
