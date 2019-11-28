1)  Save the files kustomization.yaml, mysql-deployment.yaml, wordpress-deployment.yaml in one directory.

2)  Then run following command in this directory:
    kubectl apply -k ./

3)  After a few minutes run:
    kubectl get all

    Then type in the EXTERNAL-IP of service/wordpress in browser.

4)  Currently running at URL: http://52.158.126.168/

5)  kustomization.yaml:
    Contains all the resources for deploying a WordPress site and a MySQL database and
    the used password.

6)  mysql-deployment.yaml:
    Describes a single-instance MySQL Deployment. 
    The MySQL container mounts the PersistentVolume at /var/lib/mysql. 
    The MYSQL_ROOT_PASSWORD environment variable sets the database password from the Secret. 

7)  wordpress-deployment.yaml:
    Describes a single-instance WordPress Deployment. 
    The WordPress container mounts the PersistentVolume at /var/www/html for website data files. 
    The WORDPRESS_DB_HOST environment variable sets the name of the MySQL Service defined above, 
    and WordPress will access the database by Service. 
    The WORDPRESS_DB_PASSWORD environment variable sets the database password from the Secret kustomize generated.

8)  Source: https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/