﻿# Exercise III

## WP with external database

Create the K8s resources you need to deploy a WP site on your cluster using
MariaDB as database with the characteristics below:

* All the resources should be created under the *exercise-03* namespace.
* The WP site should use a external RDS database already populated which details
are provided in the **Credentials** section.
* Use a service to connect WP wit the external database.
* Use ConfigMaps & Secrets to configure both MariaDB and WP
* Every container should have the proper readiness and liveness probes
configured
* WP should be accessible through http/https using a NGINX Ingress on the URL
*wordpress-exercise-03.com* . The ingress should handle the TLS certificates.
* WP admin panel should be accessible using a different URL, e.g.
http://wordpress-exercise-03.com/my-custom-admin/. Configure NGINX ingress to do that
redirection.

### NOTES

- rds-svc.yaml implements an externalname type of service to reach the remote database
- I've implemented the redirect with a snipped annotation because all I've tried didn't work. I know it is not the cleanest implementation
