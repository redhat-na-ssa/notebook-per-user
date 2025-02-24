I used ReadWriteMany as the storage option, but it will depend on how you want the instructors/graders to access the students' finished projects. This will be somewhat dictated by your storage solution, as different options offer different levels of accessibility.

For example, don't try to access ODF storage from outside the cluster. NFS would be totally fine, however.
