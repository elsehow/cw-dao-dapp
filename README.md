## Preview

<p align="center" width="100%">
    <img alt="cw-dao UI preview" src="https://i.imgur.com/Dtk9eyO.gif">
</p>

## Summary

This project creates a web UI around the [cw-dao](https://github.com/DA0-DA0/cw-dao) smart contract. Enabling users to:

- View proposals for a previously instantiated cw-dao
- Create proposals for sending funds from the cw-dao instance
- Vote on proposals created by other users of the cw-dao instance

## Proposal List UI

The proposal list UI provides icons indicating proposal status:

<img alt="proposal status UI table" src="https://i.imgur.com/P5FDDJ8.png">

## Development

You need to deploy the contracts to a chain running locally in order to interact with the DAO frontend.

To do this we'll use [wasmd](https://github.com/CosmWasm/wasmd) running in a docker container.

### Setup Chain

Make sure you install the `docker` command-line tool and daemon locally (Mac users can [download it here](https://docs.docker.com/desktop/mac/install/)). In a new terminal, clone the [cw-dao](https://github.com/DA0-DA0/cw-dao) repo, and run the deploy contracts script.

```bash
git clone https://github.com/DA0-DA0/cw-dao
cd cw-dao
bash scripts/deploy_local.sh
```

Make note of the addresses and private key from the output; these are the contracts deployed on a chain running in a docker container on your machine as well as the private key to an account with a balance you can import into [Kelpr](https://www.keplr.app/).

### Setup Frontend

#### Clone this repo and install dependencies

```bash
git clone https://github.com/DA0-DA0/cw-dao-dapp
cd cw-dao-dapp
yarn
```

#### Setup .env.local file

In the frontend repo, setup up your local environment

```bash
cp .env.example .env.local
```

Add the addresses from earlier.

```bash
NEXT_PUBLIC_DAO_CONTRACT_ADDRESS=wasm1nc5tatafv6eyq7llkr2gv50ff9e22mnfhap4vz
NEXT_PUBLIC_DAO_TOKEN_ADDRESS=wasm14hj2tavq8fpesdwxxcu44rty3hh90vhujgqwg3
```

Then, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

## Requirements

Please ensure you have the [Keplr wallet extension](https://chrome.google.com/webstore/detail/keplr/dmkamcknogkgcdfhhbddcghachkejeap) installed in your Chrome based browser (Chrome, Brave, etc).

## Learn More

This project was bootstrapped with [`next-cosmwasm-keplr-starter`](https://github.com/ebaker/next-cosmwasm-keplr-starter).

To learn more about Next.js, CosmJS, Keplr, and Tailwind CSS - take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.
- [CosmJS Repository](https://github.com/cosmos/cosmjs) -JavaScript library for Cosmos ecosystem.
- [@cosmjs/cosmwasm-stargate Documentation](https://cosmos.github.io/cosmjs/latest/cosmwasm-stargate/modules.html) - CosmJS CosmWasm Stargate module documentation.
- [Keplr Wallet Documentation](https://docs.keplr.app/api/cosmjs.html) - using Keplr wallet with CosmJS.
- [Tailwind CSS Documentation](https://tailwindcss.com/docs) - utility-first CSS framework.
- [DaisyUI Documentation](https://daisyui.com/docs/use) - lightweight component library built on [tailwindcss](https://tailwindcss.com/).

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
