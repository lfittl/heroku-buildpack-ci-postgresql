This solely exists as a temporary measure to fix the following error when using pg_restore inside a Heroku dyno:

```
pg_restore: [archiver] unsupported version (1.13) in file header 
```

This is caused by Heroku updating the pg:backups infrastructure to 10.3 (which has a version bump on the pg_dump/pg_restore custom format due to security reasons), whilst sadly not having updated the Heroku Dynos yet, which are still stuck on 10.1 at the time of writing.
