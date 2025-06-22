Aurora: Personal Agent Companion on Aptos
Aurora is a next-generation personal agent companion built on the Aptos blockchain, designed to empower users with a unified interface for managing their financial activities seamlessly. Leveraging the power of the Move Agent Kit and Echelon Markets, Aurora provides a comprehensive DeFi solution.

The Problem It Solves
In the DeFi ecosystem, users face challenges navigating multiple platforms to access liquidity pools, manage positions, and execute transactions. Aurora solves this by providing a unified interface powered by Echelon Markets integration.

Key Features & Implementation
Echelon Markets Integration
interface EchelonPool {
  poolId: string;
  apr: number;
  totalLiquidity: string;
  utilizationRate: number;
}

class EchelonService {
  private readonly API_BASE = 'https://api.echelon.markets';
  
  async getPoolDetails(poolId: string): Promise<EchelonPool> {
    const response = await fetch(${this.API_BASE}/pools/${poolId});
    return response.json();
  }

  async executeTransaction(type: 'supply' | 'borrow' | 'repay', params: any) {
    const signer = new LocalSigner(account, Network.TESTNET);
    const aptosAgent = new AgentRuntime(signer, aptos, {
      ECHELON_API_KEY: process.env.ECHELON_API_KEY,
    });
    return await aptosAgent.execute(type, params);
  }
}
sc-3
Key Features
Multi-wallet support and secure peer-to-peer payments
Real-time market data and analytics via Echelon
DeFi operations powered by Echelon Markets:
Borrowing, supplying, and repaying assets
Staking operations
Pool management and position creation via Joule Finance
Seamless utility payment gateway
Intuitive, user-friendly interface
Project Structure
The project consists of three main components:

Client Application
Built with React + TypeScript + Vite
Features:
Multi-wallet management and tracking
Real-time market analytics dashboard
DeFi operations interface
Utility payment gateway
Responsive UI with modern design
Agent Server
Node.js based agent implementation
Integrations:
Move Agent Kit for Aptos blockchain
Echelon Markets API
Joule Finance integration
Payment processing services
WebSocket for real-time updates
Main Server
Express.js backend
Features:
User authentication
MongoDB integration for data persistence
Wallet management APIs
DeFi operation handlers
WebSocket support for real-time communication
Getting Started
Prerequisites
Node.js (v16 or higher)
MongoDB
Yarn or npm
Aptos CLI and SDK
Installation
Clone the repository
git clone <repository-url>
cd aurora-agent
Install dependencies for all components
# Install client dependencies
cd client && yarn install

# Install agent server dependencies
cd ../agent && yarn install

# Install main server dependencies
cd ../server && yarn install
Configure environment variables
Set up Echelon Markets API keys
Configure Joule Finance integration
Set MongoDB connection string
Configure Aptos network endpoints
Start development servers
# Start client development server
cd client && yarn dev

# Start agent server
cd ../agent && yarn start

# Start main server
cd ../server && yarn start
Visit http://localhost:5173 to access the development environment.

Security
Aurora prioritizes user safety with:

Advanced encryption for data protection
Smart contract audits
Optimized gas usage
Secure wallet management
Regular security updates
Support
For support and inquiries, please open an issue in the repository or contact our support team.