---
question: "Which of the following are true regarding workflow-level vs. job-level outputs blocks?"
documentation: "https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax#example-defining-outputs-for-a-job"
---

- [ ] Job-level `outputs` blocks should only be used in caller workflows, not reusable workflows.
> Reusable workflows can have both job-level and workflow-level `outputs` blocks.
- [x] A workflow-level `outputs` block should only be used in reusable workflows, not caller workflows.
> A "workflow-level" `outputs` block refers to an `outputs` block that is a direct child of `workflow_call` in reusable workflows. In non-reusable workflows, `outputs` blocks should only be present at job-level.
- [x] A reusable workflow can have both workflow-level and job-level `outputs` blocks.
> If setting an output in a reusable workflow and passing that same output to a caller workflow is desired, both a workflow-level and a job-level `outputs` block must be used. 
> See the documentation for more details https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows#using-outputs-from-a-reusable-workflow
- [ ] A job-level `outputs` block must have the following structure:
```
outputs:
    <output-name>
        value: ${{ steps.<step-name>.outputs.<output-name> }}
```
> A job-level `outputs` block uses an un-nested structure of `key=value` pairs. See the official documentation (https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax#example-defining-outputs-for-a-job) for more details.
- [x] A workflow-level `outputs` block must have the following structure:
```
outputs:
    <output-name>
        value: ${{ jobs.<job-name>.outputs.<output-name> }}
```
> A workflow-level `outputs` block must follow the above structure. A `value` key is always required. An optional `description` key can also be used (not seen in the above example). 
> See the documentation for more details -  https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows#using-outputs-from-a-reusable-workflow