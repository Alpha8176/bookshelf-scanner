# bookshelf-scanner
AI-powered book detection from bookshelf images# BookShelf Scanner

An AI-powered web application that identifies books from photos of bookshelves using computer vision and provides detailed book information.

![BookShelf Scanner](https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&h=400)

## Features

- **Drag & Drop Upload**: Easy image upload with progress tracking
- **AI Book Detection**: Uses Google Cloud Vision API to extract text from images
- **Book Information**: Fetches detailed metadata from Google Books API
- **Beautiful Book Cards**: Displays covers, ratings, descriptions, and categories
- **Database Storage**: Persistent storage with PostgreSQL
- **Sample Images**: Test the app with provided sample bookshelf images
- **Export Functionality**: Download detected book lists

## Tech Stack

- **Frontend**: React 18, TypeScript, Tailwind CSS, shadcn/ui
- **Backend**: Node.js, Express.js, TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **APIs**: Google Cloud Vision API, Google Books API
- **Build Tool**: Vite
- **Deployment**: Ready for Replit, Vercel, or any Node.js hosting

## Quick Start

### Prerequisites

- Node.js 20+
- PostgreSQL database
- Google Cloud Vision API credentials (optional for testing)
- Google Books API key (optional for testing)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/bookshelf-scanner.git
cd bookshelf-scanner
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
# Database
DATABASE_URL=your_postgresql_connection_string

# Optional: For full AI functionality
GOOGLE_CLOUD_PROJECT_ID=your_project_id
GOOGLE_VISION_CREDENTIALS_PATH=path_to_credentials.json
GOOGLE_BOOKS_API_KEY=your_api_key
```

4. Set up the database:
```bash
npm run db:push
```

5. Start the development server:
```bash
npm run dev
```

Visit `http://localhost:5000` to see the app in action!

## Usage

1. **Upload an Image**: Drag and drop a photo of your bookshelf or click to browse files
2. **Wait for Processing**: The AI will extract text and search for books
3. **View Results**: Browse detected books with covers, ratings, and details
4. **Export List**: Download your book collection as a text file

### Sample Images

The app includes sample bookshelf images for testing without uploading your own photos.

## API Endpoints

- `POST /api/scan-bookshelf` - Upload and process bookshelf image
- `GET /api/scan/:id` - Get scan results and status
- `POST /api/process-sample/:sampleId` - Process sample images

## Project Structure

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Page components
│   │   └── lib/            # Utilities and configuration
├── server/                 # Express backend
│   ├── db.ts              # Database connection
│   ├── routes.ts          # API routes
│   └── storage.ts         # Database operations
├── shared/                 # Shared types and schemas
│   └── schema.ts          # Database schema and types
└── README.md
```

## Configuration

### Google Cloud Vision API Setup

1. Create a Google Cloud Project
2. Enable the Vision API
3. Create a service account and download the JSON key
4. Set the `GOOGLE_VISION_CREDENTIALS_PATH` environment variable

### Google Books API Setup

1. Go to Google Cloud Console
2. Enable the Books API
3. Create an API key
4. Set the `GOOGLE_BOOKS_API_KEY` environment variable

## Deployment

### Replit

This project is optimized for Replit deployment. Simply:
1. Import the project to Replit
2. Set up environment variables in Secrets
3. Click Run

### Other Platforms

The app can be deployed to any Node.js hosting platform:
- Vercel
- Railway
- Render
- Heroku

Make sure to:
1. Set environment variables
2. Provision a PostgreSQL database
3. Run database migrations

## Development

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run db:push` - Push database schema changes

### Database Schema

The app uses two main tables:
- `users` - User management (ready for future authentication)
- `book_scans` - Store scan results and detected books

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Google Cloud Vision API for text extraction
- Google Books API for book metadata
- Unsplash for sample images
- The React and Node.js communities

## Support

If you have any questions or run into issues, please open an issue on GitHub or contact the maintainers.

---

**Note**: For full AI functionality, you'll need to set up Google Cloud APIs. The app works with sample data for testing without API keys. 
