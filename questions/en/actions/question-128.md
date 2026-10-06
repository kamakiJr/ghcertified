---
question: "A workflow is triggered when pull requests are reopened. Why might this be the cause?"
documentation: "https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#pull_request"
---

- [x] `types: [reopened]` is defined under the `pull_request` event. 
- [ ] Branch protection rules were improperly configured.
> Branch protection rules do not determine when a workflow fires.
- [x] No activity types are defined under the `pull_request` event.
> If no activity types are explicitly defined, the `pull_request` event will fire off on opened PRs (`opened`), PRs whose source branch has been updated since the PR was opened (`synchronize`), or reopened PRs (`reopened`).
- [ ] `on: schedule` was configured with `pull_requests: [reopened]`
> `schedule` is used to fire workflows at certain times, not repository-based activity.
