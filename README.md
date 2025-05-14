# UIswap

UIswap is a modern decentralized exchange (DEX) interface for swapping tokens on Ethereum and other EVM-compatible blockchains. Built with Next.js and RainbowKit, UIswap provides a clean, intuitive user interface for token swapping, liquidity pool management, and portfolio tracking.

![UIswap Interface](https://placeholder.svg?height=400&width=800&query=UIswap%20Interface)

## Features

- **Token Swapping**: Easily swap between different tokens with a simple interface
- **Wallet Integration**: Connect with popular wallets via RainbowKit (MetaMask, Coinbase Wallet, etc.)
- **Portfolio Management**: Track your token holdings and transaction history
- **Liquidity Pools**: View and manage your liquidity positions
- **Multi-chain Support**: Compatible with Ethereum, Polygon, Optimism, and Arbitrum
- **Responsive Design**: Fully responsive interface that works on desktop and mobile devices
- **Dark Mode**: Built-in dark mode for comfortable viewing

## Technologies

- **Frontend**: Next.js 14 (App Router), React 18
- **Styling**: Tailwind CSS, shadcn/ui components
- **Wallet Connection**: RainbowKit, wagmi
- **State Management**: React Context API
- **Data Fetching**: TanStack Query (React Query)
- **Blockchain Interaction**: viem
- **Type Safety**: TypeScript

## Getting Started

### Prerequisites

- Node.js 18.x or later
- npm or yarn
- A WalletConnect Project ID (for wallet connections)

### Installation

1. Clone the repository:
   \`\`\`bash
   git clone https://github.com/..../uiswap.git
   cd uiswap
   \`\`\`

2. Install dependencies:
   \`\`\`bash
   npm install
   # or
   yarn install
   \`\`\`

3. Create a `.env.local` file in the root directory with your WalletConnect Project ID:
   \`\`\`
   NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID=your_project_id_here
   \`\`\`

4. Start the development server:
   \`\`\`bash
   npm run dev
   # or
   yarn dev
   \`\`\`

5. Open [http://localhost:3000](http://localhost:3000) in your browser to see the application.

## Project Structure

\`\`\`
uiswap/
├── app/                    # Next.js App Router pages
│   ├── layout.tsx          # Root layout component
│   ├── page.tsx            # Home page
│   ├── page-client.tsx     # Client-side home page component
│   ├── client-layout.tsx   # Client-side layout with providers
│   ├── metadata.ts         # App metadata
│   ├── globals.css         # Global styles
│   ├── rainbowkit.css      # RainbowKit custom styles
│   ├── pair/               # Token pair pages
│   ├── portfolio/          # Portfolio page
│   ├── pools/              # Liquidity pools page
│   └── token/              # Token detail pages
├── components/             # React components
│   ├── ui/                 # UI components (shadcn/ui)
│   ├── navbar.tsx          # Navigation bar
│   ├── footer.tsx          # Footer component
│   ├── swap-interface.tsx  # Main swap interface
│   ├── token-selector.tsx  # Token selection component
│   ├── token-provider.tsx  # Token data provider
│   ├── connect-wallet-button.tsx # Wallet connection button
│   ├── settings-dialog.tsx # Settings dialog
│   ├── recent-transactions.tsx # Recent transactions list
│   └── ...                 # Other components
├── config/                 # Configuration files
│   └── rainbow-kit.ts      # RainbowKit configuration
├── contexts/               # React context providers
│   └── wallet-context.tsx  # Wallet context provider
├── hooks/                  # Custom React hooks
│   ├── use-wallet-info.ts  # Hook for wallet information
│   └── use-wallet-connection.ts # Hook for wallet connection
├── lib/                    # Utility functions
│   └── utils.ts            # General utilities
├── public/                 # Static assets
│   ├── rainbowkit.css      # RainbowKit styles
│   └── ...                 # Images and other assets
├── services/               # Service modules
│   └── price-service.ts    # Token price service
├── next.config.mjs         # Next.js configuration
├── package.json            # Project dependencies
├── tailwind.config.ts      # Tailwind CSS configuration
└── tsconfig.json           # TypeScript configuration
\`\`\`

## Key Components

### Swap Interface

The main swap interface allows users to exchange tokens. It includes:
- Token selection
- Amount input
- Price information
- Slippage settings
- Transaction confirmation

### Wallet Connection

UIswap uses RainbowKit for wallet connections, supporting:
- MetaMask
- Coinbase Wallet
- WalletConnect
- And many other popular wallets

### Portfolio View

The portfolio page displays:
- Token balances
- Token values
- Price changes
- Transaction history

### Liquidity Pools

The pools page shows:
- Available liquidity pools
- TVL (Total Value Locked)
- APR (Annual Percentage Rate)
- User's liquidity positions

## Development

### Adding New Features

1. Create new components in the `components/` directory
2. Add new pages in the `app/` directory
3. Update context providers as needed

### Styling

UIswap uses Tailwind CSS for styling. The main theme colors and styles are defined in:
- `app/globals.css`
- `tailwind.config.ts`

### Adding New Tokens

To add new tokens, update the token list in `components/token-provider.tsx`.

## Deployment

### Vercel Deployment

The easiest way to deploy UIswap is using Vercel:

1. Push your code to a GitHub repository
2. Import the project in Vercel
3. Set the environment variables (NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID)
4. Deploy

### Docker Deployment

You can also deploy UIswap using Docker:

1. Build the Docker image:
   \`\`\`bash
   docker build -t uiswap .
   \`\`\`

2. Run the container:
   \`\`\`bash
   docker run -p 3000:3000 -e NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID=your_project_id_here uiswap
   \`\`\`

## Testing

### Running Tests

To run the tests:

\`\`\`bash
npm test
# or
yarn test
\`\`\`

### Testing Wallet Connections

For testing wallet connections, you can use the following test wallets:

- MetaMask: Install the MetaMask browser extension and create a test account
- Coinbase Wallet: Install the Coinbase Wallet browser extension
- For other wallets, you can use their respective test environments

## Security

UIswap implements several security measures:

- All transactions require explicit user confirmation
- No private keys are stored in the application
- All connections are secured with HTTPS
- Smart contract interactions are validated before execution

## Performance Optimization

The application is optimized for performance:

- Code splitting for faster initial load
- Dynamic imports for components
- Memoization of expensive calculations
- Optimized images and assets
- Server-side rendering where appropriate

## Internationalization

UIswap supports multiple languages:

- English (default)
- Spanish
- French
- German
- Chinese
- Japanese

To change the language, use the language selector in the settings menu.

## Accessibility

UIswap is designed to be accessible to all users:

- Semantic HTML
- ARIA attributes
- Keyboard navigation
- Screen reader support
- High contrast mode

## Roadmap

- [ ] Add support for more networks (Avalanche, Fantom, etc.)
- [ ] Implement token approval flow
- [ ] Add transaction history page
- [ ] Implement dark/light mode toggle
- [ ] Add ENS support
- [ ] Implement network switching UI
- [ ] Add wallet balance fetching
- [ ] Create token approval flow
- [ ] Add transaction signing
- [ ] Implement limit orders
- [ ] Add analytics dashboard
- [ ] Create mobile app version

## Troubleshooting

### Common Issues

1. **Wallet Connection Issues**
   - Make sure your wallet is unlocked
   - Check that you're on the correct network
   - Try refreshing the page

2. **Transaction Failures**
   - Ensure you have enough funds for gas
   - Check slippage tolerance settings
   - Verify token approvals

3. **UI Display Issues**
   - Clear browser cache
   - Try a different browser
   - Check for browser extensions that might interfere

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Code of Conduct

Please read our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing to the project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Next.js](https://nextjs.org/)
- [RainbowKit](https://www.rainbowkit.com/)
- [wagmi](https://wagmi.sh/)
- [shadcn/ui](https://ui.shadcn.com/)
- [Tailwind CSS](https://tailwindcss.com/)
- [viem](https://viem.sh/)
- [TanStack Query](https://tanstack.com/query)


## Contact

For questions or support, please open an issue on the GitHub repository or contact us at support@uiswap.com.

---

Made with ❤️ by the UIswap Team
