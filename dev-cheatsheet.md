# CLI Cheatsheet for Local Development

## Start a development server 

```command 
temporal server start-dev
```

- The Server is running on localhost:7233
- The Web UI can be accessed at http://localhost:8233
- This command creates a default Namespace

## Start a Workflow Execution with a Workflow Id

Start a Workflow Execution, specify the Task Queue that registers the Worker, provide the Workflow type name and supply a Workflow Id

```command
temporal workflow start --task-queue <task_queue_name> --type <workflow_type>  --workflow-id <workflow_id>
```

## List Workflows Executions of a specific Workflow Id 

```command
temporal workflow list --query "WorkflowId=<your-workflow-id>"
```

## Show information about a specific Workflow Execution 

```command
temporal workflow describe --workflow-id <workflow_id>
```

## Show the event history of a specific Workflow Execution

```command
temporal workflow show --workflow-id <workflow_id>
```

## Query a Workflow Execution

```command
temporal workflow query --workflow-id <workflow_id> --type <query_type> 
```

## Signal a Workflow Execution by Id 

```command
temporal workflow signal --workflow_id <workflow_id> --name <signal_name> --input <input_for_signal>
```

## Cancel a Workflow Execution

```command
temporal workflow cancel --workflow-id <workflow_id>
```

## Terminate a Workflow Execution 

```command
temporal workflow terminate --workflow-id <workflow_id>
```

## See information about a Task Queue 

See a list of Workers that have polled a specific Task Queue 

```command
temporal task-queue --task-queue <task_queue_name>
```

## More commands

For a full list of commands, see the [CLI docs](https://docs.temporal.io/cli) or run `temporal help`.