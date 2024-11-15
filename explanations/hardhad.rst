====================================
Installing and Setting Up Hardhat
====================================

What is Hardhat?
-----------------
Hardhat is a development environment for writing, compiling, testing, and deploying smart contracts on Ethereum. It simplifies complex workflows and provides a set of powerful tools for Solidity development.

Steps to Install and Set Up Hardhat
------------------------------------

1. **Create a Project Directory**
   Start by creating a new directory for your Hardhat project and navigate into it:

   .. code-block:: bash

      mkdir my-hardhat-project
      cd my-hardhat-project

2. **Initialize a Node.js Project**
   Initialize the project by creating a ``package.json`` file:

   .. code-block:: bash

      npm init -y

   This will create a ``package.json`` file to manage your project's dependencies.

3. **Install Hardhat**
   Install Hardhat as a development dependency:

   .. code-block:: bash

      npm install --save-dev hardhat

4. **Initialize Hardhat**
   Run Hardhat to start the setup process:

   .. code-block:: bash

      npx hardhat

   You will be prompted with several options:

   - ``Create a basic sample project``: Sets up a sample project with example contracts, scripts, and tests.
   - ``Create an empty hardhat.config.js``: Sets up a blank Hardhat configuration file.
   - ``Quit``: Exits the setup.

   Select ``Create a basic sample project`` for a guided setup.

   Hardhat will create the following directories:
   - ``contracts``: For writing smart contracts.
   - ``scripts``: For deployment and interaction scripts.
   - ``test``: For automated testing.

5. **Install Additional Dependencies**
   For interacting with smart contracts, it is recommended to install the following:

   .. code-block:: bash

      npm install --save-dev @nomiclabs/hardhat-ethers ethers

6. **Verify the Setup**
   To verify everything is installed and configured correctly, try compiling the sample project:

   .. code-block:: bash

      npx hardhat compile

   If no errors appear, your Hardhat environment is ready to use.

What's Next?
------------
After setting up Hardhat:
- Write your first smart contract in the ``contracts`` directory.
- Compile and deploy it using the provided scripts.
- Test the contract using the ``test`` directory.

For further details, visit the `official Hardhat documentation <https://hardhat.org/hardhat-runner/docs/getting-started#installation>`_.
