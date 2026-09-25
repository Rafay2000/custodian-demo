   # Troubleshooting

   ## App crashes on startup
   Usually caused by a missing or malformed `config.yaml`. Check that the
   file exists in the project root and is valid YAML.

   ## Slow performance
   Check that the database connection pool size is not set too low in
   config.yaml. The default is 5 connections.
