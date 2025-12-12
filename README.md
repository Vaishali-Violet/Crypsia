# AgriChain - Blockchain-Inspired Agricultural Supply Chain Platform

A transparent, traceable, and fair agricultural trade platform built with React, TypeScript, and Tailwind CSS. AgriChain implements a blockchain-style transaction system using Berry tokens as currency, ensuring complete product traceability from farmers to consumers.

## Features

### Multi-Role System
- **Farmer**: Create and list products for sale
- **Distributor**: Purchase from farmers and resell to retailers
- **Retailer**: Buy from distributors and sell to consumers
- **Consumer**: Purchase final products and verify authenticity via QR codes

### Core Functionality

#### Authentication & Account Management
- User registration with SHA-256 password hashing
- Multi-account support (one user can have multiple role-based accounts)
- Account switcher for seamless role transitions
- Each account has its own wallet balance

#### Berry Token Economy
- 1 Berry = ₹0.05 (Indian Rupees)
- New accounts receive 10 berries by default
- Top-up functionality to purchase more berries (simulated payment)
- 2% network fee on all transactions
- Treasury account automatically collects network fees

#### Product Management
- Auto-generated unique product codes (e.g., APL-435)
- Image upload support with Pexels stock photos
- Product categories and descriptions
- Real-time inventory tracking
- Price update functionality for unsold inventory
- Product variants for tracking split purchases

#### Blockchain-Style Transaction Chain
- SHA-256 transaction hashing
- Each transaction linked to previous transaction hash
- Immutable transaction ledger stored in localStorage
- Complete chain verification
- Product journey traceability from origin to current owner

#### QR Code System
- Auto-generated QR codes for every consumer purchase
- Scannable codes linking to transaction verification page
- Two viewing modes:
  - **My Chain**: Shows only the specific product path
  - **Full Tree**: Displays complete transaction history
- Public verification page accessible without login
- Visual transaction timeline with role indicators

#### Marketplace
- Role-based product visibility
- Category filtering (Fruits, Vegetables, Grains, Dairy, Meat, Other)
- Purchase confirmation with fee calculation
- Quantity selection for partial purchases
- Resale price setting for distributors/retailers

#### Dashboard & Analytics
- Wallet balance with INR conversion
- Total earned/spent statistics
- Transaction history
- Product inventory overview
- Real-time notifications

#### Notifications System
- Wallet creation alerts
- Low balance warnings (<5 berries)
- Purchase success/failure notifications
- Product sold notifications
- Sold-out alerts for farmers
- Unread notification counter

## Technology Stack

- **Frontend**: React 18 + TypeScript
- **Routing**: React Router DOM v7
- **Styling**: Tailwind CSS
- **Icons**: Lucide React
- **QR Codes**: qrcode.react
- **Date Formatting**: date-fns
- **Charts**: Recharts (ready for analytics)
- **Data Storage**: localStorage (can be migrated to Supabase)
- **Cryptography**: Web Crypto API (SHA-256)

## Project Structure

```
src/
├── components/
│   ├── auth/
│   │   ├── Login.tsx
│   │   ├── Register.tsx
│   │   └── AccountSelection.tsx
│   ├── layout/
│   │   ├── Header.tsx
│   │   └── Layout.tsx
│   └── products/
│       └── CreateProduct.tsx
├── context/
│   ├── AuthContext.tsx
│   └── DataContext.tsx
├── lib/
│   ├── supabase.ts
│   └── utils.ts
├── pages/
│   ├── Dashboard.tsx
│   ├── Marketplace.tsx
│   ├── Transactions.tsx
│   ├── TracePage.tsx
│   ├── MyProducts.tsx
│   └── MyInventory.tsx
├── types/
│   └── index.ts
├── App.tsx
└── main.tsx
```

## Getting Started

### Installation

```bash
npm install
```

### Development

```bash
npm run dev
```

### Build

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

## Usage Guide

### 1. Register & Create Account
1. Register with email, password, and full name
2. Create your first role-based account
3. Choose from Farmer, Distributor, Retailer, or Consumer
4. Set an account name and optional additional berry balance

### 2. As a Farmer
- Navigate to "My Products"
- Click "Create Product"
- Fill in product details (name, category, description, price, quantity, image)
- Product automatically receives a unique code
- Update prices for unsold inventory

### 3. As a Distributor
- Browse marketplace to see farmer products
- Filter by category
- Purchase full or partial quantities
- Products become variants in your inventory
- Set resale prices for retailers

### 4. As a Retailer
- View distributor variants in marketplace
- Purchase variants for resale
- Set consumer-facing prices
- Manage inventory

### 5. As a Consumer
- Browse retailer offerings
- Purchase products
- Receive QR code for product verification
- Scan QR to view complete product journey

### 6. Transaction Verification
- Click any transaction to view details
- Scan QR code or visit trace URL
- Toggle between "My Chain" and "Full Tree" views
- Verify transaction hashes and timestamps
- See complete product journey from farmer to current owner

## Key Features Explained

### Product Variants
When a product is purchased, a variant is created with:
- Unique variant code (e.g., APL-435-1, APL-435-2)
- Current owner
- Quantity
- Current resale price

This allows tracking individual product batches through the supply chain.

### Transaction Fees
Every transaction incurs a 2% network fee:
- Deducted from buyer's wallet
- Automatically credited to treasury account
- Ensures platform sustainability

### Security
- SHA-256 password hashing
- Transaction hash verification
- Chain integrity validation
- Immutable transaction history

### Data Persistence
Currently uses localStorage for:
- User accounts
- Products and variants
- Transactions
- Notifications
- Berry purchases

Can be easily migrated to Supabase database for production use.

## Future Enhancements

- Real payment gateway integration
- Advanced analytics with charts
- Email notifications
- Search and advanced filtering
- User reviews and ratings
- Mobile app with camera-based QR scanning
- Multi-language support
- Export transaction data
- Smart contract integration for true blockchain
- Geolocation for farmer verification

## License

This project is open source and available for educational and commercial use.

## Support

For issues, questions, or contributions, please contact the development team.

---

Built with ❤️ for transparent agricultural trade
