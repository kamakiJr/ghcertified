---
question: "Which of the following are true regarding calling reusable workflows versus calling composite actions?"
documentation: "https://docs.github.com/en/actions/concepts/workflows-and-actions/reusing-workflow-configurations#key-differences-between-reusable-workflows-and-composite-actions"
---

- [x] Composite actions are called via referencing the folder that contains their `action.yml` file.
> As an action, composite actions must contain the brunt of their logic within an `action.yml` file. To call the composite action, point to where its `action.yml` is located (this includes the root. ex. to call a composite action that is located at the root of the same repository as the caller workflow, the syntax `uses: ./` would be used).
- [ ] Reusable workflows are called via referencing the folder that contains their `action.yml` file.
> Reusable workflows are regular `.yml` or `.yaml` files that are stored in `.github/workflows`. They do not have an `action.yml` file.
- [x] Composite actions must be called as a step within a job
> Composite actions (as with any other action) are called from within a step of a workflow job--in other words, you do not need a specific workflow job just to caller a composite action. 
- [x] Reusable workflows must be called on workflow job level (not from step-level).
> Steps within a workflow job cannot call a reusable workflow. A reusable workflow must be called by an individual job within the caller workflow. This can result in one or more jobs running in the caller workflow (said jobs can be seen in workflow runs in the Github Actions UI). 
- [ ] Secrets can be passed to both reusable workflows and calling composite actions via the `uses.secrets` block.
> Only reusable workflows can be called using the `secrets` block. To pass secrets to a composite action, workarounds must be used (such as passing the secret as an input)
- [ ] Only reusable workflows can accept inputs.
> Both reusable workflows and composite inputs can accept inputs. 
- [x] Reusable workflows can use a different runner type than the caller workflow, while composite actions cannot. 
> Reusable workflows have jobs like any other workflow, and those jobs can specify different runner type via the `jobs.runs-on` key. Composite actions inherit the runner environment of their calling workflow job.