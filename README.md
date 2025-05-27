# MigratR
Stupid simple pure SQL migrations.

As of version 0.4.0, this tool is only compatible with mssql.
# Usage Instructions
1. Download the latest .nupkg file from releases.
2. Install it globally with `dotnet tool install --global --add-source {path_to_nupkg_parent_folder} MigratR`
> requires the .NET 9 SDK
# Commands
## `migratr init`
_Initializes a repo with a `.MigratR/config.json` file._

Inside `config.json`, there will be a field `ConnectionString`. Paste your DB connection string here.
## `migratr new [name]`
_Generates a new migration file with the date prepended to the provided name._

## `migratr up`
_Runs all migrations that have not been executed sequentially from oldest to newest._

## `migratr down [n=1]`
_Rolls back the last `n` migrations. Defaults to `1`._

# Writing a Migration File
Running `migratr new [name]` will generate a new migration SQL file that looks like this.
```sql
-- Migration: 20250526223830_sample.sql

-- UP
-- Write your forward migration SQL statements here

--//@ ```MIGRATION SEPARATOR: DO NOT DELETE THIS LINE```

-- DOWN
-- Write your rollback migration SQL statements here
```

Write all SQL statements to execute the migration above the migration separator line.
Write all SQL statements to _*roll back*_ the migration below this line.
