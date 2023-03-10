# WP Duplicator Docker-Compose

If you want to make a local clone of a WP page you can use the [Duplicator plugin](https://wordpress.org/plugins/duplicator/) and follow this instruction guide up until point 3: 
https://www.wpbeginner.com/wp-tutorials/how-to-clone-a-wordpress-site-in-7-easy-steps/

Skip point 4 and 5 and instead copy the downloaded .zip and.php files into the wp-archive folder.

You can run your local copy by executing `docker-compose up -d`.

After your containers started, navigate to `http://localhost:8000/wp-archive/installer.php`.

Continue now with the instructions from point 6. 

In the Setup step of the cloning script, enter the following values and then hit the validate button:
+ Action: Revome All Data
+ Host: db
+ Database: exampledb
+ User: exampleuser
+ Password: examplepass

These values are given in the docker-compose.yaml file. If you change them there, you also have to adjust them in the cloning process. Only use these values for local development and not in production!

Don't change anything in step 3 and continue to step 4. When you reach your admin-panel, you need to login with the credentials from your **original** page!


In case of a permission error within the duplicator setup, just change the permissions for wp-archive on your local machine by using `chmod a+rwx -R ./wp-archive`