Run the helm install in a for loop across the list of students.
```
helm package .
helm install my-class -n testuser ./single-user-jupyter-1.0.0.tgz --create-namespace
```
