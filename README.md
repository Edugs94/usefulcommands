# Useful Commands Cheatsheet 🛠️
A collection of useful command-line snippets for project evaluations, code reviews, and debugging.

## 🚀 How to Use
Copy and paste the commands below. Remember to replace placeholders like your_file.c or ./your_program with your actual file or executable names.

## 🔍 Code Auditing & Searching
Commands for finding specific code, function calls, or potential issues directly from the source.

Find specific words or function calls (e.g., malloc)
This command recursively (-r) searches all files in the current directory for the string "malloc" and shows the matching line plus the 2 lines After (-A 2) it. This is great for manually checking if all memory allocations were protected correctly.

<pre>
grep -r -A 2 malloc
</pre>

_Use -B 2 for 2 lines Before the match._

_Use -C 2 for 2 lines of Context (before and after)._

## 🧠 Memory & Debugging
Commands for checking memory leaks and runtime errors.

Prerequisite: For best results, always compile your program with the -g flag (debug symbols): 

<pre>
cc -g main.c static_library.a -o your_program
</pre>

**Valgrind** is the gold standard for memory debugging on Linux. It checks for all types of memory issues and provides a full report.

<pre>
valgrind --leak-check=full --show-leak-kinds=all ./your_program
</pre>
