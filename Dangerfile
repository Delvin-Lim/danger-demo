# Check 1: PR Description
warn("Please add a PR description.") if github.pr_body.empty?

# Check 2: PR Title
warn("PR title should have at least 10 characters") if github.pr_title.size < 10

# Check 3: PR Labels
failure("Please add a label to this PR") if github.pr_labels.empty?

# Check 4: PR Size
failure("PR size is too large") if git.lines_of_code > 500

# Check 5: Documentation
changed = git.modified_files + git.added_files
warn("UPlease update README.md") if changed.any? { |f| f.end_with?(".py") } && !changed.include?("README.md")

# Confirmation
message "Danger has completed the PR checks!"
