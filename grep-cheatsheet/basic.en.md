Certainly! I'll create a cheat sheet for grep that covers common use cases for Linux configuration, coding, and penetration testing tasks. This type of content is well-suited for an artifact, as it's a comprehensive reference that users might want to save or modify.





# Grep Cheat Sheet for Linux, Coding, and Pentesting

## Basic Syntax
```
grep [options] pattern [file...]
```

## Common Options
- `-i`: Case-insensitive search
- `-r` or `-R`: Recursive search (includes subdirectories)
- `-n`: Show line numbers
- `-w`: Match whole words only
- `-v`: Invert match (show lines that don't match)
- `-l`: Show only filenames of matching files
- `-c`: Count number of matches
- `-A n`: Show n lines after the match
- `-B n`: Show n lines before the match
- `-C n`: Show n lines before and after the match

## Linux Configuration Tasks

1. Search for a specific setting in all config files:
   ```
   grep -r "PasswordAuthentication" /etc/
   ```

2. Find all enabled services:
   ```
   grep -r "enabled=1" /etc/
   ```

3. Search for IP addresses in config files:
   ```
   grep -E -r "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" /etc/
   ```

4. Find all users with shell access:
   ```
   grep -E "/bin/(bash|sh)$" /etc/passwd
   ```

## Coding Tasks

1. Search for function definitions:
   ```
   grep -n "def " *.py
   ```

2. Find TODO comments:
   ```
   grep -r -n "TODO:" .
   ```

3. Search for specific import statements:
   ```
   grep -r "import numpy" .
   ```

4. Find all files containing a specific class:
   ```
   grep -l "class MyClass" *.py
   ```

## Penetration Testing Tasks

1. Search for potential passwords in files:
   ```
   grep -r -i "password" /path/to/search
   ```

2. Find all files containing potential API keys:
   ```
   grep -r -E "[a-zA-Z0-9]{32}" /path/to/search
   ```

3. Search for SQL injection vulnerabilities:
   ```
   grep -r -i "SELECT.*FROM.*WHERE" /var/www/html/
   ```

4. Find potential command injection vulnerabilities:
   ```
   grep -r -E "system\(|exec\(|passthru\(" /var/www/html/
   ```

5. Search for files with weak permissions:
   ```
   grep -r "777" /etc/
   ```

## Advanced Usage

1. Use OR logic:
   ```
   grep -E "pattern1|pattern2" file
   ```

2. Use AND logic:
   ```
   grep "pattern1" file | grep "pattern2"
   ```

3. Exclude certain files or directories:
   ```
   grep -r "pattern" --exclude=*.log --exclude-dir=node_modules .
   ```

4. Use regular expressions:
   ```
   grep -E "[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,4}" file
   ```

Remember to use these commands responsibly and ethically, especially for penetration testing tasks. Always obtain proper authorization before performing security assessments on systems you don't own.


I've created a comprehensive grep cheat sheet covering various use cases for Linux configuration, coding, and penetration testing tasks. This cheat sheet includes basic syntax, common options, and specific examples for each category.

Is there any particular section or type of grep usage you'd like me to explain further or expand upon?