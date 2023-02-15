
git subtree push --prefix docs wiki master

git subtree pull --prefix docs wiki master --squash --message="Merge wiki updates into docs."

## Project documentation

The project documentation (stored in the `docs` directory) is a git subtree of the [project wiki](https://github.com/<user>/<repo>/wiki). This allows for the documentation to be referenced and edited from within the main project.


### Initial local setup

When cloning the main project repository for the first time, the wiki repository must be added as a remote.

    git remote add wiki https://github.com/<user>/<repo>.wiki.git


### Adding documentation

New and updated documentation should be committed and pushed in the main project repository just like any other file.

_However, care should be taken to ensure documentation files are always committed separately from other project files. Individual commits should never contain both files inside and outside the docs directory._


### Pushing updates to the wiki

Documentation changes in the main project repository can be pushed to the wiki repository at any time. This does not need to happen every time documentation is added or updated, but can happen as often as desired.

    git subtree push --prefix docs wiki master

If the GitHub website is used to edit wiki files, the push will fail, in which case any updates should be pulled as described below.


### Pulling updates from the wiki

It should only be necessary to pull updates directly from the wiki when the GitHub website is used to edit the documentation directly in the wiki. If pushing to the wiki ever fails, try pulling first.

    git subtree pull --prefix docs wiki master --squash --message="Merge wiki updates into docs."



    docker run --rm -it -v /Users/ettienemare/Documents/Development/Divigraph:/docs -p 3000:3000 dannyben/madness server