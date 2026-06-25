# Linux File Permissions

## Project Description
The research team required authorization review across the `projects` directory. I examined existing file permissions, identified unauthorized access, and used Linux commands to remediate them — ensuring only appropriate users could access each file or directory.

---

## Tasks Performed

### 1. Check File and Directory Details
- Used `pwd` to confirm working directory: `/home/researcher2`
- Navigated to the projects directory: `cd projects`
- Listed permissions with `ls -l` and checked for hidden files using `ls -la`

### 2. Describe the Permissions String
The 10-character permission string breaks down as:

| Position | Meaning |
|----------|---------|
| 1st | File type: `d` = directory, `-` = regular file |
| 2nd–4th | User (owner) permissions: r, w, x |
| 5th–7th | Group permissions: r, w, x |
| 8th–10th | Other permissions: r, w, x |

A `-` in any position means that permission is not granted.

### 3. Change File Permissions
- **Issue:** `project_k.txt` had write permission for *others* (`-rw-rw-rw-`)
- **Fix:** `chmod o-w project_k.txt`
- **Verified:** `ls -l` confirmed updated permissions (`-rw-rw-r--`)

### 4. Change File Permissions on a Hidden File
- **File:** `.project_x.txt` (hidden, archived)
- **Issue:** Had write permissions for user and group; group lacked read permission
- **Fix:** `chmod u-w,g-w,g+r .project_x.txt`
- **Result:** Permissions changed to `-r--r-----`

### 5. Change Directory Permissions
- **Directory:** `drafts`
- **Issue:** Group had execute permission; only `researcher2` should access it
- **Fix:** `chmod g-x drafts`
- **Verified:** `ls -l` confirmed group execute permission removed

---

## Summary
Used `ls -l` and `ls -la` to audit permissions across the `projects` directory, then applied `chmod` commands to remove unauthorized access. This ensured the principle of least privilege was enforced for all files, hidden files, and subdirectories.

---

**Tools used:** Linux CLI, `chmod`, `ls -l`, `ls -la`  
**Skills demonstrated:** File permission management, Linux command line, access control
