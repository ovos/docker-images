FROM composer/satis

# Copied from: https://github.com/espressif/github-actions/pull/35/files
# Changing the ownership of the repository after checking out
# Error: fatal: detected dubious ownership in repository at '/github/workspace'
#      To add an exception for this directory, call:
#          git config --global --add safe.directory /github/workspace
# Reason: Recent versions of git require the .git folder to be owned
# by the same user (see https://github.blog/2022-04-12-git-security-vulnerability-announced/).
# Related
# - https://github.com/actions/runner/issues/2033
# - https://github.com/actions/checkout/issues/1048
# - https://github.com/actions/runner-images/issues/6775
RUN chown -R $(id -u):$(id -g) $PWD
