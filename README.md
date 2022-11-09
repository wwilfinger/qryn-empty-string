docker-composer reproduction of https://github.com/metrico/qryn/issues/242

./loki returns logs if you query `{container="some-label} |= `` `

./qryn fails with an error about the parser in the qryn container logs
