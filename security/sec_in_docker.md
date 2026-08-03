# Default docker configs
- When not declared, docker spawns all processes running as  root user.
    - Solution:
        - In docker run command, declare the user to run as.
        - Or, declare in docker file itself.
        - Or you can define scope to what privs are avail.
