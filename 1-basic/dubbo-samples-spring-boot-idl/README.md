# Dubbo Spring Boot Example using Triple and Protobuf

This example uses triple as the underlying RPC protocol and IDL to define services. It's highly recommend to use triple and IDL for cross-language communication scenarios. Please refer to [dubbo-samples-spring-boot](../dubbo-samples-spring-boot) for how to use pure Java interface to define services for triple protocol.

# How to run

## Compile

Step into 'dubbo-samples-spring-boot-idl' directory, run the following command:

```shell
$ mvn clean compile
```

## Start provider

Enter provider directory:
```shell
$ cd dubbo-samples-spring-boot-idl-provider
```

then, run the following command to start provider:
```shell
$ mvn compile exec:java -Dexec.mainClass="org.apache.dubbo.springboot.demo.provider.ProviderApplication"
```

Run the following command to see server works as expected:
```shell
curl \
    --header "Content-Type: application/json" \
    --data '{name:"Dubbo"}' \
    http://localhost:50052/org.apache.dubbo.springboot.demo.idl.Greeter/greet/
```

## Start consumer

Enter provider directory:
```shell
$ cd dubbo-samples-spring-boot-idl-consumer
```

then, run the following command to start consumer:
```shell
$ mvn compile exec:java -Dexec.mainClass="org.apache.dubbo.springboot.demo.consumer.ConsumerApplication"
```



