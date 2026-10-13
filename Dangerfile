# Check 1: PR Description
warn("PR Description empty") if github.pr_description.empty?

# Check 2: PR Title
warn("PR Title empty") if github.pr_title.empty?

# Check 3: PR Labels
failure("PR Labels not added") if github.pr_labels.empty?

# Check 4: PR Size
failure("PR size is too large") if github.lines_of_code > 500

# Check 5: Documentation
warn("Update README") if git.modified_files.any? { \|f\| f.start_with?("src/") } && !git.modified_files.include?("README.md")

# Confirmation
puts "Danger checks completed"
