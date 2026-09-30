# Troubleshooting

## App crashes on startup
Usually caused by a missing or malformed `config.yaml`. Check that the
file exists in the project root and is valid YAML.

## Slow performance
Check that the database connection pool size is not set too low in
config.yaml. The default is 5 connections.

   
## Memory grows over time
Usually caused by database connections not being released back to the pool after a
request finishes. Check that every code path that opens a connection also closes it,
including error/exception paths. Restarting the service is a temporary workaround, not
a fix.

## Last item missing from paginated results
Check the loop or slice boundary in the pagination logic. This is almost always an
off-by-one error — verify whether the comparison against page size should be `<` or `<=`.
