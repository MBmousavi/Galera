### GALERA CLUSTER FOR MYSQL
- True Multi-master,  Active-Active Cluster Read and write to any node at any time.
- Synchronous Replication No slave lag, no data is lost at node crash.
- Tightly Coupled All nodes hold the same state. No diverged data between nodes allowed.
- Multi-threaded Slave For better performance. For any workload.
- No Master-Slave Failover Operations or Use of VIP.
- Hot Standby No downtime during failover (since there is no failover).
- Automatic Node Provisioning No need to manually back up the database and copy it to the new node.
- Supports InnoDB.
- Transparent to Applications Required no (or minimal changes) to the application.
- No Read and Write Splitting Needed.
- asy to Use and Deploy
***
Use `sysctl.conf` for kernel paramaters optimization. I put my `galera.cnf` as well. It has tuned arametes for over datacenter cluster.

In my scenario I had 4 Master nodes and 1 Arbiter node(Garb Deamon). It means this cluster can handle 2 nodes failure.

GarbD is a single process that acts like a arbiter for our cluster. Maybe it can run as a service too but I didn't.

`apt install galera-arbitrator-3`

To start the GarbD process run this command. The PPID will be 1.

`/usr/bin/garbd --cfg garb_prod.txt`
