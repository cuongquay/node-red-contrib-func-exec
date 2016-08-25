# node-red-contrib-func-exec
The node-red function with child_process executable object in the sandbox context.

[![npm version](https://badge.fury.io/js/node-red-contrib-func-exec.svg)](https://badge.fury.io/js/node-red-contrib-func-exec)

**Example Flow**

```
[{"id":"18fa45e.dd993ba","type":"debug","z":"ce212a3e.f97778","name":"","active":true,"console":"false","complete":"false","x":560,"y":380,"wires":[]},{"id":"d649825e.ab13d","type":"inject","z":"ce212a3e.f97778","name":"","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"x":160,"y":300,"wires":[["3197e4b9.85addc"]]},{"id":"3197e4b9.85addc","type":"func-exec","z":"ce212a3e.f97778","name":"","func":"var exec = child_process.exec('ls -la', (error, stdout, stderr) => { \n    if (error) { \n    console.error(`exec error: ${error}`); \n    return; \n    } \n    console.log(`stdout: ${stdout}`); \n    console.log(`stderr: ${stderr}`); \n    msg.payload = stdout;\n    callback(msg);\n}); ","outputs":1,"noerr":0,"x":360,"y":340,"wires":[["18fa45e.dd993ba"]]}]
```