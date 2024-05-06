# jenkins

This is a repository created to host all learnings related to jenkins starting from basics to advanced pipelines using both
Declarative Pipelines are Scripted Pipelines using shared libraries

Pipeline Types:
```
    v1: Scripted Pipelines

    v2: DSL / Declarative Pipelines

    v3: YAML [ Still in the development phase ]

```

### Naming Standard of Jenkins Pipeline

```
Pipelines are supposed to be enclosed in a file that tend's with Jenkinsfile [ J as in Caps]

```

>>> Release Strategy :

```
1) When you push commits to feature branch: Only Lintchecks and codescan
2) When changes reach main server over a PR, that means code it stage and then if we will push a tag marking it stable
3) When we reun the job against a tag, only during that time, I want artifacts should be created and should be pushed to Nexus.

```

>>> What type of objects are supposed to be stored and where ?

```
1) Code: Plain text: Version Controlling : Github
2) Binary : Artifacts : Binary Storage [vss - version control system] : JFrog / Nexus 

```

>>> What is allow redeploy in sonanexus repository

```
Once a artifact is published, it'll never be overridden when the version is same

```

>>> How are we uploading the artifact now ?
 ```
 1) First we are creating the artifact all the time when running against a TAG
 2) Then attempting to upload the artifact :
    a) If the artifact is not available, then its uploading the artifact
    b) If the artifact already exists, then its not uploading
 ```

>>> Rather than following steps 1 & 2 :
```
1) I'd like to check the artifact first:
    a) If the artifact is available in NEXUS repo, then I don't generate artifact
    b) If the artifact is not available in NEXUS repo, then I will be generating the artifact and then uploading it.
```
### Command to check the availability of the artifact in nexus :

```
curl http://nexus_IP:8081/service/rest/repository/browse/catalogue/
```
