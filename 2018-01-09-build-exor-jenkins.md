# Building EXOR BSP on easy-jenkins

(2018-01-09 16:00 CET)

Browse <https://build.solarma.it/> (login as GitHub user "gmacario")

Open Blue Ocean > New Pipeline

* Where do you store your code? GitHub
* Which organization does the repository belong to? SOLARMA
* Choose a repository: mv-embedded-linux-course

Create Pipeline

- Build log: <https://build.solarma.it/blue/organizations/jenkins/mv-embedded-linux-course/detail/lab01-stable/1/pipeline>
- Jenkinsfile: <https://github.com/SOLARMA/mv-embedded-linux-course/blob/lab01-stable/Jenkinsfile>

**FAIL**: Excerpt from build log

```
[fsl] Running shell script
JENKINS-33510: working directory will be /var/jenkins_home/workspace/d-linux-course_lab01-stable-CVMZLMGP64TP6DWXAWAK6BBFMXI6VELKXFO5R3CBDDIUDC2AYXMA not /var/jenkins_home/fsl
+ REPO_URL=https://github.com/graugans/fsl-community-bsp-platform
+ REPO_BRANCH=jethro
+ repo init -u https://github.com/graugans/fsl-community-bsp-platform -b jethro
gpg: keyring `/home/jenkins/.repoconfig/gnupg/secring.gpg' created
gpg: keyring `/home/jenkins/.repoconfig/gnupg/pubring.gpg' created
gpg: /home/jenkins/.repoconfig/gnupg/trustdb.gpg: trustdb created
gpg: key 920F5C65: public key "Repo Maintainer <repo@android.kernel.org>" imported
gpg: key 692B382C: public key "Conley Owens <cco3@android.com>" imported
gpg: Total number processed: 2
gpg:               imported: 2  (RSA: 1)
Get https://gerrit.googlesource.com/git-repo/clone.bundle
Get https://gerrit.googlesource.com/git-repo
fatal: unable to access 'https://gerrit.googlesource.com/git-repo/': gnutls_handshake() failed: The TLS connection was non-properly terminated.

script returned exit code 1
```

TODO TODO TODO

### See also

* [Notes for EXOR](TODO)
* <https://github.com/ExorEmbedded/exor-bsp-platform>
* <https://github.com/graugans/fsl-community-bsp-platform>

<!-- EOF -->