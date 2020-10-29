# API-Branch

const octokit = new Octokit({ auth: `personal-access-token123` });

const response = await octokit.request("GET /orgs/:org/repos", {
org: "octokit",
type: "private"'
});


import { Octokit } from "@octokit/core";
import { createAppAuth } from "@octokit/auth-app";

const appOctokit = new Octokit({
  authStrategy: createAppAuth,
  auth: {
    id: 123,
    privateKey: process.env.PRIVATE_KEY,
  },
});

const { data } = await appOctokit.request("/app");

const octokit = new Octokit({
  log: require("console-log-level")({ level: "info" }),
});
