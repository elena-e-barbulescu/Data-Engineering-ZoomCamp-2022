# Week - 2 - Learning || Airflow

## Data Engineering

At a high-level, taking action to turn data into **reliable**, **repeatable**, **maintainable** process.

### What is a "workflow"?

A set of steps to accomplish a given data engineering task.  The complexity of the workflow is completely dependent on the needs of the user.


## Airflow

- a platform to program workflows, ie. creation, scheduling and monitoring.
- the workflow is written in Python (but can use components in other languages)
- implements workflows as DAGs: Directed Acyclic Graphs (a set of tasks and the dependencies between them)

    - ### Other Workflows?
        - Luigi
        - SSIS
        - Bash scripting

### What is a DAG?

It has the following attributes:

- 1 - It is **Directed**: inherent flow representing dependencies between components
- 2 - It is **Acyclic** : does not loop, cycle, or repeat
- 3 - Represents a **Graph** : the actual set of components

The "tasks": the components to be executed, such as: operators, sensors, etc.  It can be thought of at a high-level as the things in the airflow that need to be done.
- instances of operators
- assigned to a variable in Python

The task "dependencies": 
- can be defined explicitly or implicitly
- defines the execution order so airflow known at which point tasks should be done in the workflow
- not required for a given workflow, but usually present in most


### Airflow Command Line Program

- airflow - h : for descriptions
- airflow list_dags : to show all recorgnized DAGs

### Using Command Line vs. Python Code

#### Command Line:
- start airflow processes
- manually run DAGs / Tasks
- get logging information from Airflow

#### Python:
- create a DAG
- edit the individual properties of a DAG


## Most Common Task - Operators
- represents a sigle task in a workflow
- run indepedently
- do not share information between each other
- and perform independent tasks

### PythonOperator
- executes a python function that's callable
- operates similar to BashOperator, with more options
- support arguments to pass on the callabel task

## DAG Run
- a specific instance of a workflow at a point in time
- can be run manually or via "schedule_interval"
- maintain state for each workflow (and tasks within)

## Sensors
- operator that waits for a certain condition to be true (ex: creation of a file, certain response from a web request)
- can define how often to check for the condition to be true
- assigned to tasks and applied with dependencies

### Types of Sensors:
- **ExternalTaskSensor** : waits for a tasks in another DAG to complete
- **HttpSensor** : request a web URL and check for content
- **SqlSensor** : runs a SQL query to check for content


### Why use a Sensor?
- uncertain when it will be true
- if failure not immediately desired
- to add repetition without loops

## Executor
- run tasks
- handle tasks differently

Examples:
- **SequentialExecutor**
    - default executor
    - runs one task at a time
    - useful for debugging
    - not recommended for production
- **LocalExecutor**
    - treats each tasks as a process
    - relies on a single system
    - parrellelism is defined by user
    - can utilize all resources of a given host system
- **CeleryExecutor**
    - uses a "Celery" backend as a task manager
    - multiple worker systems can be defined
    - more difficult to set up and configure
    - good method for organizations with extensive workflows

