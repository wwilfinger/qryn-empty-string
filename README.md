docker-composer reproduction of https://github.com/metrico/qryn/issues/242

./loki returns logs if you query `{container="some-label} |= `` `

./qryn fails with an error about the parser in the qryn container logs

```
qryn-qryn-1        | Couldn't execute script:
qryn-qryn-1        | Expected [ 'EOF', or 'WSP' ] @1:26 encountered ' |='.
qryn-qryn-1        | {container="qryn-flog-1"} |= ``
qryn-qryn-1        | {"level":50,"time":1668010895984,"pid":19,"hostname":"d8d78a72ef7b","name":"qryn","reqId":"req-k","err":"Cannot read properties of null (reading 'rootToken')\nTypeError: Cannot read properties of null (reading 'rootToken')\n    at Object.module.exports.transpile (/app/parser/transpiler.js:90:28)\n    at Object.scanFingerprints (/app/lib/db/clickhouse.js:219:29)\n    at Object.handler (/app/lib/handlers/query_range.js:40:16)\n    at processTicksAndRejections (node:internal/process/task_queues:96:5)","msg":"Cannot read properties of null (reading 'rootToken')"}
```
