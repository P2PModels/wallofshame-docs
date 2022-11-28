# Local environment for development

## Installation
In this section we'll cover a complete installation of the development environment of the prototype.

### Download backend repo

Download the repo and install dependencies:

```bash
git clone https://github.com/p2pmodels/wallofshame-backend
cd wallofshame-backend
git checkout develop
git pull
npm install
```

### Test and deploy smart contract (optional)

If you don't have access to the smart contract instance address, you have to deploy the contract to Ethereum. The smart contract can be found inside *wallofshame-backend/smart-contracts/contracts*. We'll use hardhat to deploy but first it's recomended to run the tests:

```bash
cd smart-contracts
npx hardhat test
npx hardhat deploy --network goerli
```
Once deployed copy the generated json file from *wallofshame-backend/smart-contracts/deployments/goerli* to *wallofshame-backend/graphql-cases-service/src/report-service/abis*

### Create a subgraph (optional)

If you have deployed new instances of the smart contract, you have to create a new subgraph. Follow the instrucctions specified in [The Graph Studio](https://thegraph.com/studio/subgraph/) to create a new subgraph directory and then paste the files from *./wallofshame-backend/cases-subgraph*, compile and deploy. Check the *subgraph.yml* file to edit the basic configurations i.e. the starting block of the subgraph, the network in which it has been deployed, etc.

```bash
graph init --studio observatory-of-job-insecurity
graph auth --studio *your key*
graph codegen && graph build
graph deploy --studio observatory-of-job-insecurity
```
### Provide environment variables

Create the .env file with sensitive information for each micro service.

#### Cases service
The graphql cases service needs an end-point to connect to the blockchain (i.e. infura end-point), and a wallet (account details):

```
PUBLIC_KEY='your_wallet_account_public_address'
PRIVATE_KEY='your_wallet_account_private_address'
MNEMONIC='your_wallet_account_mnemonic'

PROJECT_ID='infura_api_key'
```

#### Users service
The graphql users service needs a conection to the db:

```
DB_URL="postgresql://user:password@server_default_localhost:port_default_5432/database"
```

#### API gateway service
The graphql API gateway needs the end-points of each micro-service:

```
USERS_API_ENDPOINT="localhost:4001/"
CASES_BACKEND_API_ENDPOINT="localhost:4002/"
CASES_SUBGRAPH_API_ENDPOINT="localhost:4002/"

```

### Build and start the services

To start the services (*graphql-cases-service* and *graphql-users-service*) we have to build the Prisma servers first:

```bash
npm run build
npm start
```

### Frontend: client webapp

To install the prototype client webapp (frontend) write the following commands on your machine:

```bash
git clone https://github.com/p2pmodels/wallofshame-frontend
cd wallofshame-frontend
git checkout develop
git pull
npm install
```

If you are going to work in localhost, enable the localhost endpoint. Uncomment the localhost endpont in file *wallofshame-frontend/src/components/BackendProvider.js* and comment the production endpoint. Then run:

```bash
npm start
```
The web app should automatically open in a new tab of your default browser.



