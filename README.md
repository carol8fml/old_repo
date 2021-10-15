# How to move a subdirectory between repositories

1. git clone https://github.com/carol8fml/old_repo.git (the old repository where the subfolder is)
2. cd old_repo
3. git filter-branch --subdirectory-filter sub_folder -f (separate subfolder locally)
4. git filter-branch -f --tree-filter 'mkdir -v sub_folder; git mv -k * sub_folder' HEAD
5. git remote set-url origin https://github.com/carol8fml/new_repo (replace the old url with the url of the new repository)
6. git fetch origin
7. git pull (if the other repository already has commits)
8. git push or git push -f  to overwrite
