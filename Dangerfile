# Check 1: PR Description
warn("PR Description empty") if github.pr_body.empty?

# Check 2: PR Title
warn("PR Title empty") if github.pr_title.empty?

# Check 3: PR Labels
failure("PR Labels not added") if github.pr_labels.empty?

# Check 4: PR Size
failure("PR size is too large") if git.lines_of_code > 500

# Check 5: Documentation
changed = git.modified_files + git.added_files
warn("Update README") if changed.any? { |f| f.end_with?(".py") } && !changed.include?("README.md")

# Confirmation
message "Danger checks completed"
