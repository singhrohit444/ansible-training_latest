* Create a role to install nginx
  * Step 1: Add a task to the role to install nginx and run the role to validate it.
  * Step 2: Add a static file to update index.html.
  * Step 3: Remove the hard-code path in index file creation and move it to variable.
  * Step 4: Instead of Static index.html file have a dynamic file.
  * Step 5: Instead of default user name in index.html pass a user name.
  * Step 6: Provide value of overridden user name from playbook.
  * Step 7: Add a handler to restart nginx in case index file gets updated & start nginx if it gets installed.
