`npm_check` is a tool that detects broken Node.js builds and sends an e-mail alert
when there is an error during the build process.

- If it is run without any parameters, it just searches for `package.json` files recursively 
starting from the current working directory and then tries to build each one.

- When it is called with `-r <URL>`, it assumes the `URL` points to a git repository and
tries to clone it and than searches for `package.json` files and then detects build errors.

- If a file is specified after `-r`, it assumes the file contains git repository `URLs`, and
iterates through the file for each `URL`. It skips empty lines and the lines starting 
with a '#'.

- The `-u` option runs `ncu -u` after a successful build and retries the build with updated 
packages.

- `-f <matches>` and `-x <matches >` options and their argument are used when `-u` is specified 
and are passed to `ncu` command as `--filter <matches>` and `--reject <matches>`

- `-q` option makes the script more silent.


