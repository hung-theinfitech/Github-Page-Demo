## Pull Request Description

### What does this PR do?

<!-- Brief description of the changes -->

### Changes Made

<!-- List of changes made -->

- [ ]
- [ ]
- [ ]

### Testing

<!-- How was this tested? -->

- [ ] Manual testing
- [ ] Automated tests pass
- [ ] Documentation updated

### Preview

📖 **Documentation Preview**: The documentation for this branch is automatically deployed and available at:

<div id="preview-link">
  <code>https://hung-theinfitech.github.io/Github-Page-Demo/[your-repo-name]/[detecting-branch...]</code>
</div>

> **Note**: Replace `[your-username]` and `[your-repo-name]` with your actual GitHub username and repository name. The branch name will be auto-detected below.

<script>
(function() {
  // Auto-detect branch name from GitHub URL
  const currentUrl = window.location.href;
  let branchName = 'unknown-branch';
  
  // Try to extract branch name from various GitHub URL patterns
  const patterns = [
    /\/compare\/([^\.]+)\.\.\./, // Compare URL pattern
    /[?&]quick_pull=([^&]+)/, // Quick pull parameter
    /\/tree\/([^\/]+)/, // Tree view pattern
    /head=([^&]+)/, // Head parameter in URL
  ];
  
  for (const pattern of patterns) {
    const match = currentUrl.match(pattern);
    if (match && match[1]) {
      branchName = decodeURIComponent(match[1]);
      break;
    }
  }
  
  // If we're in a PR creation context, try to get it from the page
  const headRefInput = document.querySelector('input[name="pull_request[head_ref]"]');
  if (headRefInput && headRefInput.value) {
    branchName = headRefInput.value;
  }
  
  // Update the preview link
  setTimeout(() => {
    const linkElement = document.getElementById('preview-link');
    if (linkElement) {
      linkElement.innerHTML = `<code>https://[your-username].github.io/[your-repo-name]/${branchName}</code>`;
    }
  }, 1000);
})();
</script>

### Checklist

- [ ] Code follows project coding standards
- [ ] Tests pass locally
- [ ] Documentation is updated (if applicable)
- [ ] Self-review completed
- [ ] Ready for review
