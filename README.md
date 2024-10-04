# TruFIU

Scalable FIU module to connect with multiple AA partners and manage consents for multiple internal applications.

## How to Run
1. Clone this repository `git clone https://github.com/getbootstack/trufiu.git`
2. Review the `.env` and `docker-compose.yaml`.
  > You can check the latest release of the docker image from the [github packages](https://github.com/orgs/getbootstack/packages/container/package/fiu-service)
3. Run `docker compose up` from `trufiu` directory.
4. You can now visit http://localhost:8080/docs/ and start exploring.

## Create an Entity in SahamatiNet / AA Ecosytem
1. Please follow the instructions outlined here: https://developer.sahamati.org.in/sahamatinet/proxy#onboarding-process
  > Entity ID, Client ID are essentially the same. It is nothing but a unique identifier of your choice for your Entity.
2. Once you have the docker container up and eunning, You may also leverage the [onboarding utils](http://localhost:8080/docs/index.html#/Utils/post_v1_utils_onboarding) to prepare your onboarding JSON payload.

## Getting Started

Its all starts with creating a app in the TruFIU. An app is nothing but the ultimate consumer of the financial information. TruFIU acts as an agent to fecilitate your interaction with the AA ecosystem. App will be notified when consent state changes and data request state changes.

1. [Create an app]( http://localhost:8080/docs/#/App/post_v1_apps_), Please note the `app_id` and `app_secret`, these credetails are required to make further API calls.
2. [Configure your FIU details](http://localhost:8080/docs/#/Entities/post_v1_entities_). You can leverage the [keypair generation](http://localhost:8080/docs/#/Utils/get_v1_utils_keypair) utils to generate the keypair to register your FIU client in the registry.
3. Add your partner [AA details]( http://localhost:8080/docs/#/Entities/put_v1_entities__fiu_client_id__aa), thats all you are all set to create consent and fetch data in the AA ecosystem
