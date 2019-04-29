# DB Instance Storage
> https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html
- DB instances for Amazon RDS for MySQL, MariaDB, PostgreSQL, Oracle, and Microsoft SQL Server use Amazon Elastic Block Store (Amazon EBS) volumes for database and log storage

## Amazon RDS Storage Types
- General Purpose SSD
- Provisioned IOPS
- Magnetic


---


# Working with Read Replicas
> https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html

- Amazon RDS uses the MariaDB, MySQL, Oracle, and PostgreSQL DB engines' built-in replication functionality to create a special type of DB instance called a Read Replica from a source DB instance. Updates made to the source DB instance are asynchronously copied to the Read Replica.
- You can reduce the load on your source DB instance by routing read queries from your applications to the Read Replica.
- Creation: When you create a Read Replica, you first specify an existing DB instance as the source. Then Amazon RDS takes a snapshot of the source instance  and creates a read-only instance from the snapshot.
- Update: Uses the asynchronous replication method for the DB engine to update the Read Replica whenever there is a change to the source DB instance.

## Overview of Amazon RDS Read Replicas
- Differences Between Read Replicas for Different DB Engines

## Creating a Read Replica

## Promoting a Read Replica to Be a Standalone DB Instance
- There are several reasons you might want to promote a Read Replica to a standalone DB instance:
    + Performing DDL operations (MySQL and MariaDB only)
    + Sharding
    + Implementing failure recovery

- steps show the general process for promoting a Read Replica to a DB instance:
    + Stop any transactions from being written to the Read Replica source DB instance, and then wait for all updates to be made to the Read Replica
    + set the read_only parameter to 0 in the DB parameter group for the Read Replica.
    + Promote the Read Replica by using the Promote Read Replica option
    + (Optional) Modify the new DB instance to be a Multi-AZ deployment

## Creating a Read Replica in a Different AWS Region
- Cross-Region Replication Considerations
- Cross-Region Replication Costs
- How Amazon RDS Does Cross-Region Replication
- Cross-Region Replication Examples

## Monitoring Read Replication
- status:
    + replicating
    + error
    + terminated
    + stopped (MySQL or MariaDB only)
    + replication stop point set (MySQL only)
    + replication stop point reached (MySQL only)

### replication lag:
+ Amazon CloudWatch by viewing the Amazon RDS `ReplicaLag` metric
+ For MySQL and MariaDB, the ReplicaLag metric reports the value of the Seconds_Behind_Master field of the SHOW SLAVE STATUS command.
- Common causes for replication lag for MySQL and MariaDB are the following:
    + A network outage.
    + Writing to tables with indexes on a Read Replica. If the read_only parameter is not set to 0 on the Read Replica, it can break replication.
    + Using a nontransactional storage engine such as MyISAM. Replication is only supported for the InnoDB storage engine on MySQL and the XtraDB storage engine on MariaDB.
- When the ReplicaLag metric reaches 0, the replica has caught up to the source DB instance.
- If the ReplicaLag metric returns -1, then replication is currently not active. ReplicaLag = -1 is equivalent to Seconds_Behind_Master = NULL.