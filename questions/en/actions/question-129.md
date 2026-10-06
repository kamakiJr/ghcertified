---
question: "`GITHUB_TOKEN` can be used to check out any repository."
documentation: "https://docs.github.com/en/actions/concepts/security/github_token#about-the-github_token"
---

- [ ] True
- [ ] Only with elevated permissions
- [x] False
> `GITHUB_TOKEN`'s permissions are scoped to the repository that contains the workflow that was triggered. 
> To check out another repository, other methods token must be used, such as a personal access token (PAT) or installation access token