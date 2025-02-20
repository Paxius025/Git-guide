# **🚀 Git Development Guide**

Git is an essential tool for software development, whether for small or large projects. 🛠️ Proper usage of Git enhances teamwork efficiency, reduces code conflicts, and allows easy rollback to previous states. 🏗️

[🇺🇸 English](README.md) | [🇹🇭 ภาษาไทย](README_th.md)

---

## **📌 Essential Git Basics for Developers**

### **1️⃣ Setting Up Git**
Before using Git, configure your user details:

```sh
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Check current configuration:
```sh
git config --list
```

---

## **📑 Best Practices for Commits**

### **✅ Writing Meaningful Commit Messages**
- Use **clear and concise descriptions**
- Start with a verb indicating the action, such as `Add`, `Fix`, `Update`
- Reference related issues or features, e.g., `Fixes #42`

#### **💡 Example of Good Commit Messages**
```sh
git commit -m "Fix: Resolve login page loading issue (Fixes #42)"  # Fixed login page loading issue (Fixes #42)
git commit -m "Feat: Add Dark Mode to UI"  # Added Dark Mode feature to UI
git commit -m "Docs: Update README with API usage instructions"  # Updated README with API usage details
git commit -m "Perf: Improve Dashboard loading performance"  # Optimized Dashboard loading speed
git commit -m "Refactor: Restructure authentication system code"  # Refactored authentication system code structure
```

---

## **🛠️ Basic Git Troubleshooting**

### **🗂️ 1. Recover Deleted Files**
If you accidentally delete a file and haven't committed yet, restore it:
```sh
git checkout -- filename
```

If the file was already committed and then deleted:
```sh
git revert HEAD -- filename
```

---

### **✏️ 2. Modify the Last Commit**
If you need to edit the last commit message or add files:
```sh
git commit --amend -m "Fix: Improve validateUser function code"  # Improved validateUser function code
```

---

### **❌ 3. Revert Uncommitted Changes**
To undo all uncommitted changes:
```sh
git reset --hard HEAD
```

To keep changes but remove the last commit:
```sh
git reset --soft HEAD~1
```

---

### **⚠️ 4. Resolving Merge Conflicts**
If a conflict occurs during a merge:
1. Open the conflicted file and manually resolve the changes.
2. Stage the resolved file:
```sh
git add resolved-file.js
```
3. Commit the merge resolution:
```sh
git commit -m "Fix merge conflict in resolved-file.js"  # Resolved merge conflict in resolved-file.js
```

---

### **⏪ 5. Reverting to a Previous Version**
To switch to a previous version while keeping changes:
```sh
git checkout commit-hash
```

To fully revert to a previous commit and discard changes:
```sh
git reset --hard commit-hash
```

---

## **🔍 Git Productivity Tips**

- **🛑 Use .gitignore** to exclude unnecessary files from commits.
- **⚡ Set up Git Aliases** to shorten commands:
  ```sh
  git config --global alias.co checkout
  git config --global alias.cm "commit -m"
  ```
- **📊 View a Clean Log History**
  ```sh
  git log --oneline --graph --decorate --all
  ```
- **🔄 Use Git Hooks** such as `pre-commit` for automatic checks before committing.

---

## **🎯 Summary**
✅ **Configure Git properly**

✅ **Create and manage branches efficiently**

✅ **Commit and push code systematically**

✅ **Keep your code updated to avoid conflicts**

✅ **Use Git Stash and Rebase for a clean workflow**

✅ **Set up Aliases and Hooks to improve efficiency**

✅ **Troubleshoot common Git issues like file recovery, conflicts, and resets**

Proper Git usage ensures a smooth development process and enhances collaboration! 🚀

