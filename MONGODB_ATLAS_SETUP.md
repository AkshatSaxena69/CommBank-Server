# MongoDB Atlas Setup Guide

## Option 1: MongoDB Atlas (Cloud) - Recommended ✓

### Steps:
1. Go to https://www.mongodb.com/cloud/atlas
2. Click "Try Free" 
3. Create an account (or login)
4. Create a free cluster:
   - Choose "Build a Cluster"
   - Select free tier (M0)
   - Choose region (Asia - Mumbai recommended for India)
   - Click "Create Cluster"
5. Wait for cluster to be created (2-3 minutes)
6. Click "Connect"
7. Choose "Drivers" and copy the connection string
8. Update `Secrets.json` with your connection string:
   ```json
   {
     "ConnectionStrings": {
       "CommBank": "mongodb+srv://username:password@cluster-name.mongodb.net/commbank?retryWrites=true&w=majority"
     }
   }
   ```
9. Replace username, password, and cluster-name with your actual values

---

## Option 2: Local MongoDB Community Edition

### Windows:
1. Download: https://www.mongodb.com/try/download/community
2. Run the installer
3. Choose "Complete" installation
4. Run MongoDB Community Server (starts automatically)
5. Use connection string: `mongodb://localhost:27017`

### Using Chocolatey (Admin required):
```powershell
choco install mongodb-community -y
```

---

## Option 3: Docker (If Docker Desktop installed)
```bash
docker run -d -p 27017:27017 --name mongodb mongo:latest
```

---

## Test Connection

After setting up, run:
```bash
cd CommBank-Server
dotnet run
```

Then test the API:
```bash
# In Postman or terminal:
curl http://localhost:5203/api/goal
```

Expected response (200 OK):
```json
[]  # Empty array initially (no data yet)
```

---

## Current Status:
- ✅ Code ready with Icon field
- ✅ Build succeeds
- ⏳ Awaiting MongoDB connection setup
- 📝 Use MongoDB Atlas for quickest setup!
