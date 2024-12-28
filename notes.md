# Serverless Apps on Cloudflare

## Commands
- ```npm create cloudflare@2.21.1 -- --no-auto-update``` Creates a new Cloudflare project
- ```npm run deploy``` Deploys the current project to Cloudflare
- ```npx wrangler d1 create [DB_NAME]``` Creates a D1 database (kinda like SQLite)
- ```npx wrangler d1 migrations create [DB_NAME] [MIGRATION_NAME]``` Creates a migration
- ```npx wrangler d1 migrations apply [DB_NAME] remote``` Applies migrations to the specified db (use ```--local``` to apply to a local db)
- ```npx wrangler secret put [SECRET_NAME]``` Creates a new secret

## Notes
- When you want to make a database change, follow these steps:
    1.  Create a new migration
    2.  Write the SQL queries to amend the database schemas
    3.  Apply any missing migrations, including the one you just wrote
- D1 databases have an automatic backup feature called 'Time Travel' that handles backups automatically
- ```workers_dev = false``` in the wrangler.toml file makes the worker private by disabling the auto-generated URL