# Steps

MySQL

    [vagrant@localhost ~]$ kubectl create -f /work/src/github.com/lshguo-qyos/community-catalog/kubernetes-templates/wordpress/1/mysql.yaml 
    service "wordpress-mysql" created
    replicationcontroller "wordpress-mysql" created
    
    [vagrant@localhost ~]$ kubectl get pods
    NAME                           READY     STATUS    RESTARTS   AGE
    apaas-452046802-zvvx6          1/1       Running   0          3d
    etcd-v3-single-un9sa           1/1       Running   0          6d
    gogs-vlmhu                     1/1       Running   0          6d
    openshift-uwnag                1/1       Running   0          2d
    registry-xn4ck                 1/1       Running   0          3d
    tidb-client-phpmyadmin-66lif   1/1       Running   0          6d
    tidb-server-esi7b              1/1       Running   2          6d
    wordpress-mysql-rdx1d          1/1       Running   0          4s
    
    [vagrant@localhost ~]$ kubectl logs wordpress-mysql-rdx1d
    Initializing database
    2016-08-17T21:02:47.346104Z 0 [Warning] InnoDB: New log files created, LSN=45790
    2016-08-17T21:02:47.471795Z 0 [Warning] InnoDB: Creating foreign key constraint system tables.
    2016-08-17T21:02:47.605933Z 0 [Warning] No existing UUID has been found, so we assume that this is the first time that this server has been started. Generating a new UUID: f35ee98c-64bd-11e6-b0ac-0242ac11000c.
    2016-08-17T21:02:47.624502Z 0 [Warning] Gtid table is not ready to be used. Table 'mysql.gtid_executed' cannot be opened.
    2016-08-17T21:02:47.625154Z 1 [Warning] root@localhost is created with an empty password ! Please consider switching off the --initialize-insecure option.
    2016-08-17T21:02:52.376800Z 1 [Warning] 'user' entry 'root@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:52.376875Z 1 [Warning] 'user' entry 'mysql.sys@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:52.376901Z 1 [Warning] 'db' entry 'sys mysql.sys@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:52.376922Z 1 [Warning] 'proxies_priv' entry '@ root@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:52.376981Z 1 [Warning] 'tables_priv' entry 'sys_config mysql.sys@localhost' ignored in --skip-name-resolve mode.
    Database initialized
    MySQL init process in progress...
    2016-08-17T21:02:56.115803Z 0 [Note] mysqld (mysqld 5.7.13) starting as process 50 ...
    2016-08-17T21:02:56.118815Z 0 [Note] InnoDB: PUNCH HOLE support available
    2016-08-17T21:02:56.118949Z 0 [Note] InnoDB: Mutexes and rw_locks use GCC atomic builtins
    2016-08-17T21:02:56.118962Z 0 [Note] InnoDB: Uses event mutexes
    2016-08-17T21:02:56.118969Z 0 [Note] InnoDB: GCC builtin __atomic_thread_fence() is used for memory barrier
    2016-08-17T21:02:56.118969Z 0 [Note] InnoDB: Compressed tables use zlib 1.2.8
    2016-08-17T21:02:56.118986Z 0 [Note] InnoDB: Using Linux native AIO
    2016-08-17T21:02:56.119284Z 0 [Note] InnoDB: Number of pools: 1
    2016-08-17T21:02:56.119828Z 0 [Note] InnoDB: Using CPU crc32 instructions
    2016-08-17T21:02:56.122847Z 0 [Note] InnoDB: Initializing buffer pool, total size = 128M, instances = 1, chunk size = 128M
    2016-08-17T21:02:56.129847Z 0 [Note] InnoDB: Completed initialization of buffer pool
    2016-08-17T21:02:56.131524Z 0 [Note] InnoDB: If the mysqld execution user is authorized, page cleaner thread priority can be changed. See the man page of setpriority().
    2016-08-17T21:02:56.143286Z 0 [Note] InnoDB: Highest supported file format is Barracuda.
    2016-08-17T21:02:56.166238Z 0 [Note] InnoDB: Creating shared tablespace for temporary tables
    2016-08-17T21:02:56.166371Z 0 [Note] InnoDB: Setting file './ibtmp1' size to 12 MB. Physically writing the file full; Please wait ...
    2016-08-17T21:02:56.216812Z 0 [Note] InnoDB: File './ibtmp1' size is now 12 MB.
    2016-08-17T21:02:56.219342Z 0 [Note] InnoDB: 96 redo rollback segment(s) found. 96 redo rollback segment(s) are active.
    2016-08-17T21:02:56.219373Z 0 [Note] InnoDB: 32 non-redo rollback segment(s) are active.
    2016-08-17T21:02:56.219772Z 0 [Note] InnoDB: Waiting for purge to start
    2016-08-17T21:02:56.271550Z 0 [Note] InnoDB: 5.7.13 started; log sequence number 2524437
    2016-08-17T21:02:56.277811Z 0 [Note] InnoDB: Loading buffer pool(s) from /var/lib/mysql/ib_buffer_pool
    2016-08-17T21:02:56.280263Z 0 [Note] Plugin 'FEDERATED' is disabled.
    2016-08-17T21:02:56.292815Z 0 [Note] InnoDB: Buffer pool(s) load completed at 160817 21:02:56
    2016-08-17T21:02:56.294479Z 0 [Warning] Failed to set up SSL because of the following SSL library error: SSL context is not usable without certificate and private key
    2016-08-17T21:02:56.358105Z 0 [Warning] 'user' entry 'root@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:56.358307Z 0 [Warning] 'user' entry 'mysql.sys@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:56.358565Z 0 [Warning] 'db' entry 'sys mysql.sys@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:56.358656Z 0 [Warning] 'proxies_priv' entry '@ root@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:56.361978Z 0 [Warning] 'tables_priv' entry 'sys_config mysql.sys@localhost' ignored in --skip-name-resolve mode.
    2016-08-17T21:02:56.370852Z 0 [Note] Event Scheduler: Loaded 0 events
    2016-08-17T21:02:56.372248Z 0 [Note] mysqld: ready for connections.
    Version: '5.7.13'  socket: '/var/run/mysqld/mysqld.sock'  port: 0  MySQL Community Server (GPL)

wordpress

    [vagrant@localhost ~]$ kubectl create -f /work/src/github.com/lshguo-qyos/community-catalog/kubernetes-templates/wordpress/wordpress-controller.yaml 
    You have exposed your service on an external port on all nodes in your
    cluster.  If you want to expose this service to the external internet, you may
    need to set up firewall rules for the service port(s) (tcp:30701) to serve traffic.
    
    See http://releases.k8s.io/HEAD/docs/user-guide/services-firewalls.md for more details.
    service "wordpress" created

![wordpress page](./屏幕快照%202016-08-17%20下午3.21.49.png)

phpMyAdmin

    [vagrant@localhost ~]$ kubectl create -f /work/src/github.com/lshguo-qyos/community-catalog/kubernetes-templates/wordpress/phpmyadmin.yaml 
    You have exposed your service on an external port on all nodes in your
    cluster.  If you want to expose this service to the external internet, you may
    need to set up firewall rules for the service port(s) (tcp:32096) to serve traffic.
    
    See http://releases.k8s.io/HEAD/docs/user-guide/services-firewalls.md for more details.
    service "phpmyadmin-wordpress" created
    replicationcontroller "phpmyadmin-wordpress" created

![phpMyAdmin page](./屏幕快照%202016-08-17%20下午3.22.32.png)