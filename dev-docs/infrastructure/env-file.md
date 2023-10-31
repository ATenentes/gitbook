---
description: Env configuration for athena-web frontend repository
---

# ENV File

### [Environment Variables](https://github.com/AthenaDexFi/athena-web#environment-variables) <a href="#user-content-environment-variables" id="user-content-environment-variables"></a>

To run this project, you will need all the variable specified in the .env file.

To configure various aspects of Athena, you need to set up environment variables. These variables are used to define URLs, addresses, and other settings needed for the proper functioning of the application.

Create a `.env` file in your project's root directory and add the required variables along with their values. Here's a sample `.env` file:

* **VITE\_APP\_BACKEND\_URL**="The URL of the backend server"
* **VITE\_APP\_RPC\_URL**: "The URL for the RPC connection."
* **VITE\_APP\_FACTORY\_ADDRESS**: "The address of the factory contract."
* **VITE\_APP\_ADDRESS\_IDO\_POOL**: "The address for the IDO pool."

\-**VITE\_APP\_ADDRESS\_ATH\_TOKEN**: "The address for the ATH token."

* **VITE\_APP\_ADDRESS\_QUEUE\_INFO**: "The address for queue information."
* **VITE\_APP\_ADDRESS\_ATH\_STAKING**: "The address for ATH staking."
* **VITE\_APP\_ADDRESS\_ATHENA\_LAUNCHPAD\_INFO**: "The address for Athena launchpad information."
* **VITE\_APP\_ADDRESS\_ATH\_REFERRAL**: "The address for ATH referral."
* **VITE\_APP\_ADDRESS\_QUEUE\_FACTORY**: "The address for the queue factory."
* **VITE\_APP\_ADDRESS\_SHORT\_FACTORY**: "The address for the short factory."
* **VITE\_APP\_ADDRESS\_ATHENA\_LAUNCHPAD\_POOL\_FACTORY**: "The address for Athena launchpad pool factory."
* **VITE\_APP\_ADDRESS\_ATH\_QUEUE**: "The address for ATH queue."
* **VITE\_APP\_ADDRESS\_ATH\_TRADER**: "The address for ATH trader."
* **VITE\_APP\_ADDRESS\_ATH\_SHORT**: "The address for ATH short."
* **VITE\_APP\_ADDRESS\_ATH\_TRADER\_CEX**: "The address for ATH trader CEX."
* **VITE\_APP\_ADDRESS\_PRESALE\_TOKEN**: "The address for the presale token."
* **VITE\_APP\_ADDRESS\_TEST\_CURRENCY**: "The address for the test currency."
* **VITE\_APP\_ADDRESS\_TEST\_TOKEN**: "The address for the test token."

1. Create a `.env` file in your project's root directory.
2. Add the variables and their values in the format `VARIABLE_NAME=value`.

```
  VITE_APP_BACKEND_URL=""
  VITE_APP_BACKEND_URL=""
  VITE_APP_BACKEND_URL=""
  VITE_APP_RPC_URL=""
  VITE_APP_RPC_URL=
  VITE_APP_FACTORY_ADDRESS=
  VITE_APP_ADDRESS_IDO_POOL=""
  VITE_APP_ADDRESS_ATH_TOKEN=""
  VITE_APP_ADDRESS_QUEUE_INFO=""
  VITE_APP_ADDRESS_ATH_STAKING=""
  VITE_APP_ADDRESS_ATHENA_LAUNCHPAD_INFO=""
  VITE_APP_ADDRESS_ATH_REFERRAL=""
  VITE_APP_ADDRESS_QUEUE_FACTORY=""
  VITE_APP_ADDRESS_SHORT_FACTORY=""
  VITE_APP_ADDRESS_ATHENA_LAUNCHPAD_POOL_FACTORY=""
  VITE_APP_ADDRESS_ATH_QUEUE=""
  VITE_APP_ADDRESS_ATH_TRADER=""
  VITE_APP_ADDRESS_ATH_SHORT=""
  VITE_APP_ADDRESS_ATH_TRADER_CEX=""
  VITE_APP_ADDRESS_PRESALE_TOKEN=""
  VITE_APP_ADDRESS_TEST_CURRENCY=""
  VITE_APP_ADDRESS_TEST_TOKEN=""
```

Save the .env file. Do not share this file, as it contains sensitive information. These variables are crucial for your project's functionality. They'll be automatically loaded by the application when it starts.
