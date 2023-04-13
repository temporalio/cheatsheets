# Temporal CLI Cheatsheet for Temporal Operators 

The new Temporal CLI replaces Temporalite and `tctl`. 

## Connecting to a Production Cluster 
 
When you are connecting to a production Cluster you will need to provide connection and client options including:

* An address and port number.
* A NamespaceLink preview icon Name (like a Temporal Cloud Namespace: <Namespace_ID>.tmprl.cloud).
* mTLS CA certificate.
* mTLS private key.

## Workflow Commands

### Start a Workflow Execution 

Start a Workflow Execution and specify the Task Queue that registers the Worker 

```command
temporal workflow start --task-queue <task_queue_name>
```

Start a Workflow Execution and manually set the workflow identifier

```command
temporal workflow start --workflow-id <workflow_id>
```

### Schedule an Operation

Create a schedule

```command
temporal schedule create --schedule-id <schedule_id> --task-queue <task_queue_name> ----workflow-type <workflow_type_name>
``` 

### See information about a Workflow Execution

Show information about a specific Workflow Execution 

```command
temporal workflow describe --workflow-id <workflow_id>
```

Show the event history for a specific Workflow Execution

```command
temporal workflow show --workflow-id <workflow_id>
```

### Manage Activities 

Complete an Activity 

```command
temporal activity complete --activity-id <activity_id>
```

Fail an Activity 

```command
temporal activity fail --activity-id <activity_id>
```

### Get Information about a Task Queue

See the Workers that have polled a Task Queue 

```command 
temporal task-queue describe  --task-queue <task_queue_name>
```

### Reset a Workflow Execution

Reset a Workflow by workflow ID 

```command
temporal workflow reset --workflow-id <workflow_id>
```

Reset a batch of Workflow Executions by reset type

```command 
temporal workflow batch-rest --type <reset_type>                

```
Reset types: `FirstWorkflowTask`, `LastWorkflowTask`, or `LastContinuedAsNew`

### Delete a Workflow Execution

Delete a specific Workflow Execution using a workflow ID 

```command 
temporal workflow delete --workflow-id <workflow_id>
```

Delete all Workflow Executions in a namespace 

```command 
temporal workflow delete --namespace <namespace_name>
```
   