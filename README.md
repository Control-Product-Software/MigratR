# MigratR
Stupid simple pure SQL migrations.

As of version 0.4.0, this tool is only compatible with mssql.
# Usage Instructions
1. Download the latest .nupkg file from releases.
2. Install it globally with `dotnet tool install --global --add-source {path_to_nupkg_parent_folder} MigratR`
> requires the .NET 9 SDK
# Commands
- `migratr init` - run this command once in a repo to initialize it with a .MigratR/config.json
- `migratr new` - generate a new migration file with the date prepended
- `migratr up` - run all migrations that have not been run
- `migratr down [n=1]` - rollback the last `n` migrations. Defaults to `1`
