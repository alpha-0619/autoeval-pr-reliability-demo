Demo pull requests for the Autoeval PR Reliability Report. Each one runs the Autoeval suite gate in GitHub Actions, and the report shows up as a comment on the PR. Since 16 October 2026 the workflow installs the published @plumloom/cli@0.1.5 from npm. Before that it built the CLI from the feat/pr-reliability-report branch of AlchemyInCode/plumloom-autoeval-oss at commit bf58d8b, and those earlier runs are still in each pull request's checks history.

Each pull request adds one suite manifest at evals/autoeval.suite.yaml. Every suite mixes a live scenario, a frozen conversation and a frozen agent trace:

- PASS: https://github.com/alpha-0619/autoeval-pr-reliability-demo/pull/1
- FAIL: https://github.com/alpha-0619/autoeval-pr-reliability-demo/pull/2
- INCONCLUSIVE: https://github.com/alpha-0619/autoeval-pr-reliability-demo/pull/3

The workflow is that repository's example suite-gate workflow with two changes. It reads the judge and primary model IDs from secrets instead of variables, so GitHub masks them in the public logs, and it prints the installed CLI path and version so the log shows which package ran. That's all that's different.

The eval files in evals/ are copied unchanged from that repository's examples. Apache-2.0, see LICENSE and NOTICE.
