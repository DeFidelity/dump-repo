Apologies for the confusion. It appears that the `updatedb` and `locate` commands are not available in your WSL environment. These commands are typically part of the `mlocate` package, which may not be installed by default in your Ubuntu WSL setup.

To resolve this issue, you can try the following steps:

1. Update the package list: Run the following command to update the package list in your Ubuntu WSL environment:
   ```
   sudo apt update
   ```

2. Install the `mlocate` package: Run the following command to install the `mlocate` package, which provides the `updatedb` and `locate` commands:
   ```
   sudo apt install mlocate
   ```

3. Build the initial database: After installing `mlocate`, you need to build the initial database used by the `locate` command. Run the following command:
   ```
   sudo updatedb
   ```

4. Search for the `flyctl` executable: Once the database is updated, you can search for the `flyctl` executable using the `locate` command:
   ```
   locate flyctl
   ```

   Look for the output that includes the path to the `flyctl` executable.

If the installation of the `mlocate` package or the execution of the commands encounter any errors, please provide the specific error messages so that I can assist you further.

Great! Now that you have the location of the `flyctl` executable, you can add it to the PATH environment variable by following these steps:

1. Open your WSL user profile file (`~/.bashrc`) in a text editor using the `nano` command:
   ```
   nano ~/.bashrc
   ```

2. Add the following line at the end of the file, replacing `/home/amusat-haki/.fly/bin` with the actual directory path you obtained:
   ```
   export PATH="$PATH:/home/amusat-haki/.fly/bin"
   ```

3. Save the changes by pressing Ctrl+O, then press Enter to confirm. Exit the text editor by pressing Ctrl+X.

4. Either restart your terminal or run the command:

```source ~/.bashrc```

 to apply the changes to the current session.

After these steps, you should be able to use the `flyctl` command directly from anywhere within the WSL environment.

To verify if the PATH has been updated correctly, you can run `echo $PATH` in the terminal. It should display the updated PATH with the added directory containing `flyctl`.

If you are using a different shell, such as Zsh, you would need to modify the corresponding profile file (e.g., `~/.zshrc`) instead of `~/.bashrc`.

Let me know if you have any further questions!


If you're encountering difficulties using the `nano` editor to modify the `~/.bashrc` file, you can try an alternative method to clean it up and add the `flyctl` executable to the PATH by running commands.

Here's an alternative approach to clean up the `~/.bashrc` file and add the `flyctl` executable to the PATH using commands:

1. Clean up the `~/.bashrc` file:
   - Create a backup of the `~/.bashrc` file, just in case:
     ```
     cp ~/.bashrc ~/.bashrc_backup
     ```

   - Remove the existing `~/.bashrc` file:
     ```
     rm ~/.bashrc
     ```

   - Generate a new, clean `~/.bashrc` file:
     ```
     echo 'export PATH="$PATH:/home/amusat-haki/.fly/bin"' > ~/.bashrc
     ```

2. Apply the changes:
   - Reload the updated `~/.bashrc` file to apply the changes:
     ```
     source ~/.bashrc
     ```

3. Verify the PATH:
   - Confirm that the `flyctl` executable is now in the PATH:
     ```
     which flyctl
     ```

   - It should display the location of the `flyctl` executable, indicating that it has been added to the PATH successfully.

By following these steps, you will create a new `~/.bashrc` file with the `flyctl` executable added to the PATH. This approach avoids editing the file manually and allows you to achieve the desired result through commands.

```
locate pre-commit | grep bin/pre-commit$
```

reduce number of machines running on fly.io to 1:
```
 fly scale count --app handlefinder-database 1
```
scale to zero link:
https://fly.io/docs/postgres/managing/scale-to-zero/

start celery:
celery -A sherlock_rest_service worker -l INFO

