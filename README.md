# NX Test
This is a test repo for troubleshooting an issue related to nx.

After cloning this repo, cd into `workspace` and clone the following:
https://github.com/ngageoint/opensphere
https://github.com/ngageoint/opensphere-plugin-geopackage

Globally install `pnpm`

After cloning `pnpm install` to install deps

`pnpm nx init` fails so I manually added a nx.json file

`pnpm nx graph` succeeds but gives empty graph

Also included an example multipackage script at `pnpm run lint-all`

This should provide the minimum level of set up to reproduce the issue.


### One more thing
We reference our internal deps a little differently so after cloning you may want to change the dependency in `workspace/opensphere-plugin-geopackage/package.json` from `"opensphere": "0.0.0-development"` to `"opensphere": "workspace:*"`

### Notes
`"cacheDirectory": "~/nx"` in `nx.json` is not what we really use, we use a shared mount
We also set `export NX_PROJECT_GRAPH_CACHE_DIRECTORY="/opt/dev/nx"` so our `nxdeps.json` files don't stomp on eachother


reference:
https://nrwlcommunity.slack.com/archives/CMFKWPU6Q/p1663264619089729

original repo:
https://github.com/ngageoint/opensphere-yarn-workspace
