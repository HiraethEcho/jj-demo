# jj-demo

A demo repository for trying out [Jujutsu (jj)](https://github.com/martinvonz/jj) - a powerful Git-compatible version control system.

## What is Jujutsu?

Jujutsu (jj) is a modern version control system designed to be simple, fast, and powerful. Key features include:

- **Git-compatible**: Works with existing Git repositories
- **Simple mental model**: Every change is automatically recorded
- **Conflict resolution**: First-class conflict handling
- **Undo/redo**: Powerful operation history
- **Working copy as commit**: The working copy is treated as a commit

## Installation

### macOS
```bash
brew install jj
```

### Linux (Cargo)
```bash
cargo install jj-cli
```

### Other platforms
See the [official installation guide](https://martinvonz.github.io/jj/latest/install-and-setup/).

## Getting Started

### Initialize jj in this repository
```bash
# Clone this repo if you haven't already
git clone https://github.com/HiraethEcho/jj-demo.git
cd jj-demo

# Initialize jj (creates .jj directory alongside .git)
jj git init --colocate
```

### Basic Commands

#### Check status
```bash
jj status  # or jj st
```

#### View history
```bash
jj log
```

#### Create a new change
```bash
# Make some edits to files, then:
jj describe -m "Your commit message"
jj new  # Start a new change
```

#### Edit commit messages
```bash
jj describe -m "New message"
```

## Demo Scenarios

### Scenario 1: Basic Workflow
```bash
# 1. Create a file
echo "Hello, Jujutsu!" > hello.txt

# 2. Check status (changes are already tracked!)
jj status

# 3. Describe the current change
jj describe -m "Add hello.txt"

# 4. Start a new change
jj new

# 5. View the log
jj log
```

### Scenario 2: Amending Changes
```bash
# 1. Edit hello.txt
echo "Hello again!" >> hello.txt

# 2. Squash into the previous commit
jj squash

# 3. View the result
jj log
```

### Scenario 3: Working with Branches
```bash
# 1. Create a bookmark (jj's term for branch)
jj bookmark create feature-branch

# 2. Make changes and commit
echo "Feature work" > feature.txt
jj describe -m "Add feature"

# 3. View bookmarks
jj bookmark list
```

### Scenario 4: Undo Operations
```bash
# View operation history
jj op log

# Undo the last operation
jj undo
```

## Useful Resources

- [Jujutsu Documentation](https://martinvonz.github.io/jj/latest/)
- [Jujutsu GitHub Repository](https://github.com/martinvonz/jj)
- [Tutorial: Getting Started with Jujutsu](https://martinvonz.github.io/jj/latest/tutorial/)

## Tips

1. **Working copy is a commit**: In jj, your working directory is always a commit. No need to stage files.
2. **Use `jj log`**: The log view is powerful and shows the change graph clearly.
3. **Don't be afraid to experiment**: `jj undo` can reverse almost any operation.
4. **Git interop**: Use `jj git push` and `jj git fetch` to interact with Git remotes.

---

Happy experimenting with Jujutsu! 🥋