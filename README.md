socket read timeout when initilizating connection

 - SocketInputStream.read() - impl.gettimeout ==> 0
 - LoggingManagedHttpClientConnection.setSocketTimeout() sets the timeout 
 - MainClientExec.execute(): 
    ```java
               final int timeout = config.getSocketTimeout();
                if (timeout >= 0) {
                    managedConn.setSocketTimeout(timeout);
                }
```

 - HttpComponentsClientHttpRequestFactory.createRequest() and createRequestConfig() -- *this is where the context get created*


