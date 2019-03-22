# lfs-testrepo

This repo is for personal testing with git and LFS.

Having committed both from a local repo _with_ LFS installed (1) and drom another local repo (for the same remote) _without_ LFS installed (2), my conclusion is that both repos MUST have LFS installed to successfully track and commit large files.

- it seems that repo 2 is able to update an LFS-file (already pushed to the remote from repo 1), without LFS-versioning for this file, both in repo 2 **and on github**!
It would have been better if github just refused such an upload, and expects an LFS-pointer for this file.
So, while the previous version was stored on github with LFS, the updated version is now stored directly in the repository!
- While the above observations seem still more or less 'logical' (but to be avoided / not ideal), an extra problem arises in repo 1, where the file is locally tracked by LFS.
After having done the git pull, the git status still shows that the LFS-file is in a modified state.
This must be because git LFS does not see the actual LFS-file in the working directory mirrored in its local LFS storage.
