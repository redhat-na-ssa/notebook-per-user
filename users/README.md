Run the helm install in a for loop across the list of students.
```
helm package .
helm install my-group -n my-class ./single-user-jupyter-1.0.0.tgz --create-namespace --set "users={testuser}" --set "groups.mygroup={user1,user2}"
```

Using the "users" value creates workbenches for each individual user. If instead you use "groups", give the group a name and specify the users in the group. The Helm chart will handle both in any combination.

## Alternate RBAC

The presented approach currently has some rough edges in the OpenShift AI Console. You can simplify this through an alternate approach, which comes at the cost of having to maintain a centralized ClusterRole. 

Alternatively to the role permissions, you can find the `edit` ClusterRole, grab all of its `rules`, and build a new ClusterRole with all of them *except* `get` for `kubeflow.org.notebooks`.

Then in your `templates/role.yaml` you only need `kubeflow.org.notebooks` and for the appropriate `resourceName`. You will also need to bind all of your users to the new ClusterRole in the target namespace.