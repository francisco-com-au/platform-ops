# ArgoCD apps

Contents of this folder will be syncrhonised to the cluster.

Here you define ArgoCD applications, projects and other stuff related to ArgoCD. The applications themselves will then point to any helm or git repo, including this one.

For platform specific apps, you can use the folder `/apps` to define your manifests and then reference them in your ArgoCD apps defined here.