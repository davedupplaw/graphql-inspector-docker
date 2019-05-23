# graphql-inspector in a docker container
Docker build for [graphql inspector](https://graphql-inspector.com) for CI builds

Useful for validating GraphQL documents against schemas within a CI build.

To use, for example:

```
docker run -v $PWD:/app -ti davedupplaw/graphql-inspector graphql-inspector validate /app/myQuery.graphql /app/schema.graphql
```

or add into a GitLab CI YAML, something like:

```
Validate GraphQL Queries:
  stage: test
  script:
  - graphql-inspector validator myQuery.graphql schema.graphql
```