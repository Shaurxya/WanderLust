# WanderLust

A premium Airbnb-style property listing platform built with Node.js, Express, MongoDB, and EJS.

## Features

- Browse property listings with beautiful card-based UI
- Create, edit, and delete listings
- Responsive design with modern aesthetics
- Search functionality
- Premium navigation and user interface

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB (MongoDB Atlas for production)
- **Template Engine**: EJS with ejs-mate
- **Styling**: Bootstrap 5, Custom CSS
- **Fonts**: Plus Jakarta Sans

## Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/Shaurxya/WanderLust.git
   cd WanderLust
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory:
   ```
   MONGO_URL=mongodb://127.0.0.1:27017/wanderlust
   NODE_ENV=development
   ```

4. Seed the database (optional):
   ```bash
   npm run seed
   ```

5. Start the server:
   ```bash
   npm start
   ```

6. Open your browser and navigate to `http://localhost:8080/listings`

## Deployment to Vercel

### Prerequisites
- A Vercel account connected to your GitHub
- A MongoDB Atlas account with a cluster set up

### Steps

1. **Set up MongoDB Atlas**:
   - Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
   - Create a free cluster
   - Get your connection string (looks like: `mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/wanderlust?retryWrites=true&w=majority`)
   - Make sure to replace `<username>` and `<password>` with your actual credentials
   - Whitelist all IPs (0.0.0.0/0) in Network Access for Vercel

2. **Deploy to Vercel**:
   - Go to [Vercel Dashboard](https://vercel.com/dashboard)
   - Click "Add New..." → "Project"
   - Import your `WanderLust` repository
   - In **Environment Variables**, add:
     - Name: `MONGO_URL`
     - Value: Your MongoDB Atlas connection string
   - Click "Deploy"

3. **Seed your production database** (optional):
   - After deployment, you can run the seed script with your production MONGO_URL:
   ```bash
   MONGO_URL=<your-atlas-url> npm run seed
   ```

### Important Notes
- The `MONGO_URL` environment variable **MUST** be set in Vercel for the deployment to work
- Local MongoDB (`mongodb://127.0.0.1:27017/wanderlust`) will NOT work on Vercel
- Vercel will automatically redeploy when you push to the main branch

## Troubleshooting

### Internal Server Error on Vercel
- Check that you've added the `MONGO_URL` environment variable in Vercel
- Verify your MongoDB Atlas connection string is correct
- Ensure MongoDB Atlas allows connections from all IPs (0.0.0.0/0)
- Check Vercel deployment logs for specific error messages

### Local Development Issues
- Make sure MongoDB is running locally
- Check that the port 8080 is not already in use
- Verify all dependencies are installed with `npm install`

## License

ISC
