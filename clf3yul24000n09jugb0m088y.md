---
title: "Bash shell finds out if a variable has a NULL value OR not"
datePublished: Sat Mar 11 2023 12:51:53 GMT+0000 (Coordinated Universal Time)
cuid: clf3yul24000n09jugb0m088y
slug: bash-shell-finds-out-if-a-variable-has-a-null-value-or-not
tags: bash-shell-finds-out-if-a-variable-has-a-null-value-or-not

---

In the Bash shell, you can use the `-z` option to check if a variable has a null (empty) value or not. Here's an example:

```bash
if [ -z "$my_var" ]; then
  echo "my_var is null or empty"
else
  echo "my_var is not null or empty"
fi
```

In the above example, `$my_var` is the variable that you want to check for null or empty value. The `-z` option checks if the length of the string in `$my_var` is zero, which means that it is null or empty.

Alternatively, you can use the `-n` option to check if a variable has a non-null value. Here's an example:

```bash
if [ -n "$my_var" ]; then
  echo "my_var has a value"
else
  echo "my_var is null or empty"
fi
```

In the above example, the `-n` option checks if the length of the string in `$my_var` is non-zero, which means that it has a value.