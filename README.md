
# gRPC-webui

👨‍💻Like Postman, but for gRPC: web based GUI client for gRPC Development Testing

Turn [gRPCli](https://github.com/gogoods/grpcli) into web based UI, extremely easy to use

## Features
- Recognize and provide list of services and methods inside it as an options.
- Automatically recognize schema input and compose it into JSON based. (ensure your gRPC server supports [server reflection](https://github.com/grpc/grpc/blob/master/src/proto/grpc/reflection/v1alpha/reflection.proto)). Examples for how to set up server reflection can be found [here](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md#known-implementations).
- Save established connection, and reuse it for next invoke/request (also can close/restart connection)
- Support request metadata.
- Support load test to method.

## Installation

### Docker Compose

```shell
docker-compose up
```
if you're using docker and want to connect gRPC on your local machine, then use
<br/>`host.docker.internal:<your gRPC port>` instead of `localhost`

### Golang
if you have golang installed on your local machine, just run command
```shell
make start
```

configure app preferences by editing `config.env` file

| var             | usage                                       | type   | unit   |
|-----------------|---------------------------------------------|--------|--------|
| MAX_LIFE_CONN   | maximum idle time connection before closed  | number | minute |
| TICK_CLOSE_CONN | ticker interval to sweep expired connection | number | second |

set value `0 (zero)` to disable auto close idle connection.

## Demo
![gRPCox Demo](./assets/grpc-webui.png)


![gRPCox Demo](./assets/grpc-webui.webp)
