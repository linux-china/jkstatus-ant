JK Status Ant Tasks
=============================
Ant tasks for mod_jk, such as status display, worker switch etc.

### mod_jk Setup
  * Please use htpasswd to create passwords file. htpasswd -c /etc/httpd/conf/passwords admin
  * Modify httpd.conf file and add following code:

          <Location "/jkstatus">
                  Order allow,deny
                  Allow from all
                  AuthType Basic
                  AuthName "Restricted JK Status"
                  AuthUserFile /etc/httpd/conf/passwords
                  Require user admin
          </Location>
          JkMount /jkstatus/* jkstatus
  * Visit http://foobar.com/jkstatus

### Example
* Display load balancer status
* Stop or Active worker for deployment

### Document

* [jkstatus tasks](http://tomcat.apache.org/connectors-doc/miscellaneous/jkstatustasks.html)
