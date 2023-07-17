# Manual Health State SCOM Management Pack

Agent task to set the state of the 'Entity Health' monitor of any object. Typically I've used this for making dashboards reflect the true state of the environment and for demo'ing MPs.

* [MP Download](MPs)
* [Visual Studio Solution](<Manual Health State>)

> **Remember**: 'Entity Health' is an aggregate monitor. It won't update it's health state unless a child monitor changes health state. If you set it to warning, it won't change state until one of it's children changes state or you set it again.  

## Set Monitor Health State Task

Targeted at System.Entity has an overridable parameter 'Health State'. Which is the state to set the monitor to. 'Success', 'Warning', or 'Error'. Default is 'Success'. The tasks sets the state of 'Entity Health' (System.Health.EntityState).

## Using the Task

>Task is targeted at System.Entity and will be available in the tasks pane for all objects in SCOM
![Set Entity Health Monitor State Task](<Screencaps/Set Entity Health Monitor State Task.png>)

>In my example, before running the task, Health Explorer shows the 'Entity Health' monitor as critical   
![Alt text](<Screencaps/Health Explorer Before.png>)

>Override the state you want to set the monitor to 'Success', 'Warning', or 'Error'.
![Alt text](<Screencaps/Set Entity Health Monitor State Task Override.png>)

>After running the task, Health Explorer shows the 'Entity Health' monitor as warning (the value I overrode the task with).   
![Alt text](<Health Explorer After.png>)
