# Release process

## Manual

1. Make sure your repo is clean by git's standards
2. If this is a new minor release, create a new release branch and push to github, for example `release-0.2`
3. Tag the repository and push the tag `git tag -s -m $VERSION $VERSION`
4. Create a draft release in github and associate it with the tag that was just created
5. Checkout the tag you've just created and make sure git is in a clean state
6. Run `make release`
7. Attach the files in the `out` directory to the drafted release:
    1. `clusterawsadm-darwin-amd64`
    2. `clusterawsadm-linux-amd64`
    3. `infrastructure-components.yaml`
8. Perform the [image promotion process](https://github.com/kubernetes/k8s.io/tree/master/k8s.gcr.io#image-promoter)
9. Write the release notes (see note below on release notes)
10. Publish release
11. Email `kubernetes-sig-cluster-lifecycle@googlegroups.com` to announce the release

### Release Notes

Running `make release-notes` will generate an output that can be copied to the drafted release.
Pay close attention to the `## :question: Sort these by hand` section, as it contains items that need to be manually sorted.


