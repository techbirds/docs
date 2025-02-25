<!-- Snippet used in the following topics:
- /docs/concepts/resources/revisions.md
- /docs/serving/revisions/README.md
-->
Revisions are Knative Serving resources that contain point-in-time snapshots of the application code and configuration for each change made to a Knative Service.
<!--Stateless taken from https://github.com/knative/specs/blob/main/specs/serving/knative-api-specification-1.0.md#revision
TODO: Update API spec docs to be consistent w/ docs site?-->

You cannot create Revisions or update a Revision spec directly; Revisions are always created in response to updates to a Configuration spec. However, you can force the deletion of Revisions, to handle leaked resources as well as for removal of known bad Revisions to avoid future errors when managing a Knative Service.

Revisions are generally immutable, except where they may reference mutable core Kubernetes resources such as ConfigMaps and Secrets. Revisions can also be mutated by changes in Revision defaults. Changes to defaults that mutate Revisions are generally syntactic and not semantic.

<!--TODO: Add info about relationship between revisions and operator vs other types of installations or deployments?-->
