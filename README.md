File Sharing App
A simple file-sharing application built with Node.js, Express, and MongoDB. Users can upload files, generate sharable links, download files, and send email notifications with file download links.

Features
Upload files to the server
Generate sharable download links for uploaded files
Download files using generated links
Send email notifications with download links
Prerequisites
Node.js (v14 or later)
MongoDB (for local or cloud instances)
Installation
Clone the Repository
sh
Copy code
git clone https://github.com/your-username/file-sharing-app.git
cd file-sharing-app
Install Dependencies
sh
Copy code
npm install
Set Up MongoDB
Ensure you have MongoDB installed and running locally. Create a new database named myDatabase:

sh
Copy code
mongo
use myDatabase
Alternatively, set up a cloud MongoDB instance (e.g., MongoDB Atlas) and use the provided connection string.

Configure Environment Variables
Create a .env file in the root directory of the project and add the following configuration:

env
Copy code
DATABASE_URI=mongodb://localhost:27017/myDatabase
BASE_URL=http://localhost:10000
Replace mongodb://localhost:27017/myDatabase with your MongoDB connection string if using a cloud instance.

Start the Application
sh
Copy code
node app.js
The server will start on port 10000 by default.

API Endpoints
1. Upload File
Endpoint: POST /api/file

Form-Data Parameters:

attachment: The file to upload.
Response:

json
Copy code
{
  "success": true,
  "message": "File uploaded successfully",
  "fileId": "file_id_here"
}
2. Generate Sharable Link
Endpoint: GET /file/:fileId

Parameters:

fileId: The ID of the file.
Response:

json
Copy code
{
  "success": true,
  "message": "Generate sharable link API",
  "result": "/files/download/file_id_here"
}
3. Download File
Endpoint: GET /files/download/:fileId

Parameters:

fileId: The ID of the file.
Response: Downloads the file.

4. Send Email
Endpoint: POST /api/files/send

Body Parameters:

fileId: The ID of the file.
email: The recipient's email address.
Response:

json
Copy code
{
  "success": true,
  "message": "Mail sent successfully"
}
Development
To run the application in development mode with automatic restarts:

sh
Copy code
npm run dev
This uses nodemon to watch for file changes and automatically restart the server.

Testing
No tests are included in this version. You can add tests using tools like Mocha, Chai, or Jest.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Contributing
Feel free to open issues or submit pull requests. Your contributions are welcome!

