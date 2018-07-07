<h1 align="center">Truffle and React.js</h1> <br>
<p align="center">
  <img alt="comet" src="https://user-images.githubusercontent.com/943555/35969146-a360d406-0d11-11e8-8224-2efdde6fb888.png" width="120">
</p>
<p align="center">Rapid Ethereum Dapp Development</p>

<p align="center">
  <img alt="made for ethereum" src="https://img.shields.io/badge/made_for-ethereum-771ea5.svg">
  <img alt="to the moon" src="https://img.shields.io/badge/to_the-moon-fab127.svg">
  <img alt="MIT license" src="https://img.shields.io/badge/license-MIT-blue.svg">
</p>

---

## Smart Contract Development with Create-React-App

How does this differ from the official React Truffle Box?

- **No ejection** required;
- **React frontend** is located in its own separate folder (i.e. `/client`);
- **Babel** is included so you can use ES6 module import statements;
- Uses **Web3 1.0 beta** with **PromiEvents**
- Truffle-Contract is no longer a dependency

If you have Truffle installed, run the following to get started (more detailed instructions below):

```
truffle unbox adrianmcli/truffle-react
```

---

**Note:** This Truffle box works by creating a symlink in the `client/src` directory to the `build/contracts` folder generated by Truffle compiled JSON files (i.e. when `truffle compile` is run). Because of this, we cannot support Windows machines at this time. Windows users can still use this Truffle box, but they will have to make the symlink themselves (as per the `link-contracts` npm script located inside `client/package.json`). If anyone can integrate Windows support for this project, feel free to discuss in the issues and submit a PR.

Consider consulting the [Truffle-Next](https://github.com/adrianmcli/truffle-next) project for a more streamlined React development process.

This Truffle Box is still in early development, there is much work to be done. Any issues and PRs are welcome.

## Installation

1. Install Truffle globally.
    ```javascript
    npm install -g truffle
    ```

2. Download the box. This also takes care of installing the necessary dependencies.
    ```javascript
    truffle unbox adrianmcli/truffle-react
    ```

3. Run the development console.
    ```javascript
    truffle develop
    ```

4. Compile and migrate the smart contracts. Note inside the development console we don't preface commands with `truffle`.
    ```javascript
    compile
    migrate
    ```

5. Run the webpack server for front-end hot reloading (outside the development console). Smart contract changes must be manually recompiled and migrated.
    ```javascript
    // Change directory to the front-end folder
    cd client
    // Serves the front-end on http://localhost:3000
    npm run start
    ```

6. Truffle can run tests written in Solidity or JavaScript against your smart contracts. Note the command varies slightly if you're in or outside of the development console.
    ```javascript
    // If inside the development console.
    test

    // If outside the development console..
    truffle test
    ```

7. Jest is included for testing React components. Compile your contracts before running Jest, or you may receive some file not found errors.
    ```javascript
    // Make sure you are inside the client folder
    cd client
    // Run Jest outside of the development console for front-end component tests.
    npm run test
    ```

8. To build the application for production, use the build command. A production build will be in the build_webpack folder.
    ```javascript
    // Make sure you are inside the client folder
    cd client
    // Run the build script
    npm run build
    ```

## FAQ

* __How do I use this with the EthereumJS TestRPC?__

    It's as easy as modifying the config file! [Check out our documentation on adding network configurations](http://truffleframework.com/docs/advanced/configuration#networks). Depending on the port you're using, you'll also need to update line 24 of `src/utils/getWeb3.js`.

* __Why is there both a truffle.js file and a truffle-config.js file?__

    `truffle-config.js` is a copy of `truffle.js` for compatibility with Windows development environments. Feel free to it if it's irrelevant to your platform.

* __Where is my production build?__

    The production build will be in the build_webpack folder. This is because Truffle outputs contract compilations to the build folder.

* __Where can I find more documentation?__

    This box is a marriage of [Truffle](http://truffleframework.com/) and a React setup created with [create-react-app](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md). Either one would be a great place to start!
