# [REPO IS ARCHIVED] Maintained version lives [here](https://github.com/everscale-tools/msig-assistant)

# Everscale MultiSig Assistant

## What is it?

This product monitors and confirms transactions for multisig wallets.

It's easily configurable and capable of managing multiple "transaction routes" in multiple networks.

It might prove useful to validators whose wallets require additional transaction confirmations (`reqConfirms` > 1).

## Have it Up & Running

- Refer to [config.js.example](config.js.example) to create `./config.js` file
- Create `./docker-compose.yml` using example below and deploy the service:
    ```yaml
    version: "2.3"
    services:
      freeton-msig-assistant:
        image: sergemedvedev/freeton-msig-assistant
        environment:
          DEBUG: "app,lib:*"
        volumes:
          - type: bind
            source: ./config.js
            target: /usr/src/app/config.js
            read_only: true
        restart: always
    ```
    ```console
    $ docker-compose up -d
    ```
