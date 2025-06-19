# 23ai_vm_tls

## Purpose
Info for a successful config of one way TLS on the Oracle supplied 23ai Developer Days VM

## Server Config Steps

1. Create cert using instructions in server/wallet/create_server_wallet.txt
2. Create directory and server wallet using instructions in server/wallet/create_server_wallet.txt
3. Configure Server using sqlnet.ora parameters
4. Configure listener using listener.ora parameters
5. Restart listener

## Client Config Steps
1. Create directory and client wallet using cert generated in (1) above
2. Configure client sqlnet.ora
3. Configure client tnsnames.ora, note protocol=TCPS and wallet specified in sqlnet.ora or explicitly in tnsname
4. Make a connection
5. Verify using verify.sql - should return "tcps" as network_protocol

## To Do
1. Verify ciphers negotiated by turning on tracing
2. Determine if SSL_VERSION or SSL_CIPHER_SUITES should be explicitly - at least on server side
3. Determine why same client config from 19.3 client on windows does not work
