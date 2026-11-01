# credfeto-inbucket

[Configurator](https://inbucket.org/configurator/)

## Watchtower

[Watchtower](https://github.com/nicholas-fedor/watchtower) keeps the containers up to date.

- Old images are removed after an update (`WATCHTOWER_CLEANUP` is enabled).
- Update checks run on the schedule in `WATCHTOWER_SCHEDULE`, which defaults to `0 36 * * * *` (36 minutes past every hour).

`WATCHTOWER_SCHEDULE` is a six-field cron expression with seconds first:

```text
seconds minutes hours day-of-month month day-of-week
```

To override the schedule, copy `.env.example` to `.env` next to `docker-compose.yml` and change the value, for example:

```env
WATCHTOWER_SCHEDULE="0 0 4 * * *"
```

Docker Compose reads `.env` automatically. Do not commit `.env`.
