<img 
    style="display: block; 
           margin-left: auto;
           margin-right: auto;
           width: 60%;"
    src="https://github.com/artis-project/artis-project.github.io/assets/69470817/c343854b-4a3a-4b26-85d2-54abb64ce6f9" 
    alt="Our logo" />

ARTIS-project is a artwork tracking prototype system combining IoT and Blockchain to innovate the process of artwork transportation. The following are the major components of the system:

- [artis-rockpi-logger:](https://github.com/artis-project/artis-rockpi-logger) Using a Radxa rockpi board and a DHT-22 sensor the logger records temperature and humidity data while the artwork is in transit. The logger can be configured with predefined temperature and humidity thresholds and reports any violation to the artis-server.
- [artis-server:](https://github.com/artis-project/artis-server) The artis-server is a Flask service designed to be deployed to Google Cloud as a Cloud Run service. It exposes a REST API to register a new artwork with the system, add necessary details, update information, and report violations. The API connects to a smart contract deployed on the Ethereum testnet sepolia.
- [artis-smartcontract:](https://github.com/artis-project/artis-smartcontract) The smart contract written in Solidity defines an ERC-721 NFT token that digitally represents an artwork. Each token stores details about the artwork including the actors of the transporation process. This includes the carrier, owner, recipient, and logger. All of these actors / components are identified by their Ethereum account. Additonally, the smart contract implements a role based authorization that manages read / write access to the artwork data.
- [artis-frontend:](https://github.com/artis-project/artis-frontend) To easily authenticate and interact with the system, the project includes a small user interface. The frontend consists of three main views: login view, home view, detail view. The login view guides the user through the authentication process, which uses the Metamask wallet to sign a message to provide proof-of-ownership. The home view shows an overview of all artwork IDs the user is registered with and a button that creates a new artwork NFT. The detail view is presented if the user clicks on a specific artwork ID and shows all the detail about the artwork. This includes the status of the artwork, a timestamp of the latest violation (if any) and more. Check it out:

<div style="text-align: center;">
    <a href="https://artis-project.github.io/artis-frontend"> https://artis-project.github.io/artis-frontend</a>
</div>

## More information
To read more about the artis-project visit <a href="https://artis-project.github.io/artis-thesis">https://artis-project.github.io/artis-thesis</a>
