opsworks_delayed_job
====================

These recipes set up an [AWS OpsWorks](http://aws.amazon.com/opsworks/) instance to run [delayed_job](https://github.com/collectiveidea/delayed_job) workers for a Rails application.


Configuration Examples
----------------------

   {
      "delayed_job": { "pool_size": 3, "path_to_script": "bin" }
    }


OpsWorks Set-Up
---------------

Create a custom layer for the delayed_job instances. Add the `AWS-OpsWorks-Rails-App-Server` security group to the layer, so that the instances have the usual cache and database access. Then, assign this cookbook's custom chef recipes to OpsWorks events as follows:

* **Setup**: `opsworks_delayed_job::setup`
* **Configure**: `opsworks_delayed_job::configure`
* **Deploy**: `opsworks_delayed_job::deploy`
* **Undeploy**: `opsworks_delayed_job::undeploy`
* **Shutdown**: `opsworks_delayed_job::stop`