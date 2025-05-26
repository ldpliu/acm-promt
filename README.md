# Why
When interacting with AI tools to execute operations on an ACM cluster, there is a high degree of behavioral uncertainty in current AI systems, and the responses from different LLM often lack consistency.

Provide a tools/MCP server to use AI to make ACM more easy to use, and make the AI tool behavior more accurate and controlled. With this, user could chat with ACM in Cursor/Cline easily.

# use cases
When I send the following request to collective env, I expect the result to be deterministic.

## clusters 
1. claim a cluster from latest cluster pool
2. create a clusterpool based on latest ocp 4.19 images
3. get user passwd/ consol link of a cluster.
4. import cluster <xxx> to xxx
5. create a acm hub
6. hibernate all my clusters
7. resume all my clusters
8. create a cronjob to hierbernate all clusters in ns

## policies
1. enable all policy to all aws clusters

# process -> suggestion

