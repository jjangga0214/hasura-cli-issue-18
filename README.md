# hasura-cli-issue-18

This is reproduction repo for [hasura-cli#18](https://github.com/jjangga0214/hasura-cli/issues/18).

The project structure is based on [jjangga0214/hasura-starter](https://github.com/jjangga0214/hasura-starter).

Note that [`.nvmrc`](./.nvmrc) is set to `v10.15.2`.

## Reproduction steps

Simply run these commands.

```bash
# Install hasura-cli@1.0.0-rc.1
npm install

# Place .env and edit if you want.
# Hasura's endpoint will be http://localhost:57679 by default.
# If you changed hasura's endpoint, edit config.yaml as well.
# (you don't have to edit docker-compose.yml directly)
cp .env.example .env

# run Hasura and Postgres
docker-compose up -d

# Open browser and wait(reload) until Hasura becomes ready
# This automatically opens $HASURA_ENDPOINT
npm run openbrowser

# Run the reproduction command
npm run repro
```

If the `npm run repro` script shows the result like the below, there's no problem.

```
VERSION        NAME  SOURCE STATUS  DATABASE STATUS
1573631107183  init  Present        Present
```

## Personal Result

In my local machine(`linux`), I found no issue with given environment(`http`).