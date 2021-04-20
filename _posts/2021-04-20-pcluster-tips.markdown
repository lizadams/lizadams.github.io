---
layout: post
title:  "pcluster tips"
date:   2020-04-20
categories: tips
---
Using pcluster to run cmaq from the `shared` directory.

Note, it is possible to adjust the configuration options with the exception of changing the HEAD node. I tried changing from t2.large to c5.xlarge and it said to create a new cluster.
Creating a new cluster would require re-installing all of the software.

```
(apc-ve) (base) liz-mbp:~ lizadams$ pcluster update cmaq
Retrieving configuration from CloudFormation for cluster cmaq...
Validating configuration file ...
Found Configuration Changes:

#    parameter             old value    new value
---  --------------------  -----------  -----------
     [cluster default]
01*  master_instance_type  t2.large     c5.xlarge

Validating configuration update...
The requested update cannot be performed. Line numbers with an asterisk indicate updates requiring additional actions. Please review the details below:

#01
Update actions are not currently supported for the 'master_instance_type' parameter
How to fix:
Restore 'master_instance_type' value to 't2.large'. If you need this change, please consider creating a new cluster instead of updating the existing one.

In case you want to override these checks and proceed with the update please use the --force flag. Note that the cluster could end up in an unrecoverable state.
Update aborted.
```

I found a nice site that has some ideas of how to do that: https://jiaweizhuang.github.io/blog/aws-hpc-guide/#motivation-and-principle-of-this-guide
