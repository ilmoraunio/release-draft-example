# Release drafter

Creates a draft to a specified tag that is kept up-to-date with specified branch. Will delete draft and re-create until de-drafted.

By default, both PR titles and commit subjects are printed on the release draft. If you wish to make a release, just add a tag and subject of your own choosing to a draft and publish!

```bash
% bb .github/scripts/release-notes --owner "ilmoraunio" --repository "release-draft-example" -a "main" -b "v0.0.1"
* Pin update-tag action to a full SHA for safety #1
* Remove unused fn 5f8a391
```

Can be configured to include only PRs:

```bash
% bb .github/scripts/release-notes --owner "ilmoraunio" --repository "release-draft-example" -a "main" -b "v0.0.1" --ignore-commits
* Pin update-tag action to a full SHA for safety #1
```

Or to include just commit subjects:

```bash
% bb .github/scripts/release-notes --owner "ilmoraunio" --repository "release-draft-example" -a "main" -b "v0.0.1" --ignore-prs
* Remove unused fn 5f8a391
* Merge pull request #1 from ilmoraunio/pin-update-tag-with-sha 31c4689
```

```
% bb .github/scripts/release-notes -h
      --owner OWNER            Owner or parent organization or repository
      --repository REPOSITORY  Repository name
  -a, --start-ref REF          Ref (inclusive) where to start gathering revision list from
  -b, --stop-ref REF           Ref (exclusive) where to stop gathering revision list
      --ignore-commits         Omits commit titles from release notes output
      --ignore-prs             Omits PR titles from release notes output
      --escape-newlines
  -h, --help
```
