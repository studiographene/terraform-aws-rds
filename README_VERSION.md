# v1.4.1

### What:

> Fix

Parameter group parameters to support blue/green deployment

#### Why:

Fix `logical_replication` parameter group parameters to support blue/green deployment

#### info:

# v1.4.0

### What:

> New Feature

Blue/Green update: enabled by default, it requires `backup_retention_period` > 0.
Blue/Green update can be disabled by setting `enable_blue_green_update = false`.

> Enhancement

Security group name is suffixed with `rds` for easy identity.

> Breaking change

SG will be recreated with same configs. If you have created SG rules for this RDS SG, you may have to remove those rules as well temporarily and add it back if `Terraform apply` gets stuck at destroying the RDS SG.

#### Why:

Earlier SG name had only Label Context label `id`.

#### info:

New variable

```
variable "enable_blue_green_update" {
  description = "Whether to enable RDS blue green update. Requires `backup_retention_period` > 0."
  type        = bool
  default     = true
}
```

# You can find the previous versions' release note at GitHub
