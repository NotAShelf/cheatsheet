# Git Cheatsheet

Useful Git commands or command combinations.

## List All Unique Authors

```bash
git log --format='%aN <%aE>' | sort -u
```

- `%aN`: Author name
- `%aE`: Author email
- `sort -u`: Sort and deduplicate

### Variants

```bash
git log --format='%aN' | sort -u   # Names only
git log --format='%aE' | sort -u   # Emails only
```

## Find First (Oldest) Commit by an Author

By Author Name (partial match works):

```bash
# Replace "Author" with the Git username that you are looking for
# E.g., NotAShelf
git log --reverse --all --author="Author" --pretty=format:"%H %ad %an <%ae>" --date=iso | head -n 1
```

By Specific Email:

```bash
# Replace "E-mail" with the Git e-mail that you are looking for
# E.g., raf@notashelf.dev
git log --reverse --all --author="E-mail" --pretty=format:"%H %ad %an <%ae>" --date=iso | head -n 1
```

- `--reverse`: Show oldest commits first
- `--all`: Search across all branches
- `--author`: Match commits by author name/email
- `--pretty=format:`: Custom output (must be followed by a format line)
- `--date=iso`: Human & machine readable date
- `head -n 1`: Show only the first result
