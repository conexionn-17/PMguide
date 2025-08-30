# 🚀 **Complete PM Internship Portal - Backend Setup Guide**

## 📋 **Overview**
This guide will help you set up the backend for PM Internship Portal with:
- **Backend**: Flask API with Supabase database
- **Resume Analysis**: AI-powered resume parsing and scoring
- **Internship Management**: CRUD operations, search, filters
- **Database**: Supabase PostgreSQL integration

---

## 🏗️ **Backend Project Structure**
```
PM-Internship-Portal/
├── app.py                 # Main Flask application
├── config.py              # Configuration and environment variables
├── database.py            # Database operations
├── resume_parser.py       # Resume analysis logic
├── import_data.py         # CSV data import script
├── requirements.txt       # Python dependencies
├── .env                   # Environment variables 
├── test_api.py            # Backend testing
├── start_portal.py        # Easy startup script
├── download_nltk_data.py  # NLTK data downloader
└── Final Dataset PM Internship CSV.csv  # Your data file
```

---

## 🔧 **Step 1: Environment Setup**

### **1.1 Create .env File**
Create a file named `.env` in your project directory:

```bash
# .env file content
SUPABASE_URL=https://your-project-id.supabase.co
SUPABASE_KEY=your-anon-key-here
FLASK_ENV=development
FLASK_DEBUG=True
```

**How to get Supabase credentials:**
1. Go to [Supabase Dashboard](https://supabase.com/dashboard)
2. Select your project
3. Go to Settings → API
4. Copy Project URL and anon public key

### **1.2 Install Python Dependencies**
```bash
# Install all required packages
pip install -r requirements.txt

# Or install individually if requirements.txt doesn't work:
pip install flask flask-cors supabase python-dotenv pdfplumber python-docx pyresparser spacy nltk
```

### **1.3 Download NLTK Data**
```bash
python download_nltk_data.py
```

---

## 🗄️ **Step 2: Database Setup**

### **2.1 Create Table in Supabase**
- Go to your Supabase dashboard
- Click "Table Editor"
- Create a new table named `internships`
- Or use the import script to create it automatically

### **2.2 Import Your CSV Data**
```bash
python import_data.py
```

**Or manually upload:**
- Go to Supabase → Table Editor → internships
- Click "Insert Row" or use the import feature
- Copy data from your CSV file

---

## 🚀 **Step 3: Start Backend**

### **3.1 Start Flask Server**
```bash
python app.py
```

**Expected output:**
```
 * Serving Flask app 'app'
 * Debug mode: on
 * Running on http://127.0.0.1:5000
```

### **3.2 Test Backend (in new terminal)**
```bash
python test_api.py
```

**Expected output:**
```
✅ Home endpoint working
✅ Internships endpoint working
✅ Locations endpoint working
✅ Stats endpoint working
✅ Search endpoint working
✅ Pagination working
```

---

## 🧪 **Step 4: Testing & Verification**

### **4.1 Backend Health Check**
```bash
# Test if backend is running
curl http://localhost:5000/
# Should return JSON response
```

### **4.2 API Testing**
1. Run `python test_api.py`
2. Should show all green checkmarks
3. Verify database connection works

### **4.3 Resume Analysis Test**
1. Test resume analysis endpoints
2. Verify file upload works
3. Check text analysis functionality

---

## 🔍 **Troubleshooting Common Issues**

### **Issue 1: Missing Dependencies**
```bash
# Check what's missing
python -c "import flask, supabase, dotenv; print('All good!')"

# Install missing packages
pip install package-name
```

### **Issue 2: Environment Variables Not Loading**
```bash
# Test environment loading
python -c "from config import Config; print('✅ Environment loaded!')"

# Check .env file exists and has correct values
# Make sure no spaces around = signs
```

### **Issue 3: Database Connection Failed**
```bash
# Verify Supabase credentials in .env
# Check internet connection
# Verify table exists in Supabase
```

### **Issue 4: Resume Analysis Not Working**
```bash
# Check NLTK data is downloaded
python download_nltk_data.py

# Verify all packages installed
pip list | grep -E "(nltk|spacy|pdfplumber|docx)"
```

---

## 🎯 **Quick Start Commands (Copy & Paste)**

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Download NLTK data
python download_nltk_data.py

# 3. Start backend
python app.py

# 4. Test backend (in new terminal)
python test_api.py
```

---

## 📚 **API Endpoints Reference**

### **Internship Management**
- `GET /internships` - List all internships
- `GET /internships/{id}` - Get specific internship
- `POST /internships` - Create new internship
- `PUT /internships/{id}` - Update internship
- `DELETE /internships/{id}` - Delete internship

### **Search & Filters**
- `GET /internships?search=keyword` - Search internships
- `GET /internships?department=IT` - Filter by department
- `GET /internships?location=Mumbai` - Filter by location
- `GET /internships?page=1&limit=10` - Pagination

### **Statistics**
- `GET /stats` - Get dashboard statistics
- `GET /departments` - List all departments
- `GET /locations` - List all locations

### **Resume Analysis**
- `POST /api/analyze-resume` - Analyze uploaded file
- `POST /api/analyze-resume-text` - Analyze text input
- `GET /api/resume-templates` - Get resume templates
- `GET /api/resume-skills` - Get skills lists

---

## 🎉 **Success Indicators**

Your backend setup is complete when:
- ✅ Backend runs on `http://localhost:5000`
- ✅ API tests pass with green checkmarks
- ✅ Database connection established
- ✅ Resume analysis endpoints work
- ✅ All CRUD operations functional
- ✅ Search and filter endpoints respond

---

## 🚀 **Advanced Features**

### **Resume Analysis Capabilities**
- **File Support**: PDF, DOCX, DOC files
- **Text Extraction**: Intelligent parsing of resume content
- **ATS Scoring**: Applicant Tracking System compatibility
- **Skills Analysis**: Technical, soft, and business skills
- **Suggestions**: Actionable improvements for resumes
- **Keyword Matching**: Industry-specific skill identification

### **Internship Management Features**
- **Advanced Search**: Multi-criteria search functionality
- **Smart Filtering**: Department, location, qualification filters
- **Pagination**: Efficient handling of large datasets
- **Statistics Dashboard**: Real-time data insights

---

## 🔧 **Backend Customization**

### **API Customization**
- Add new API endpoints in `app.py`
- Modify database schema in `database.py`
- Enhance resume analysis in `resume_parser.py`

### **Data Customization**
- Update CSV structure for different internship types
- Modify skills keywords in resume analysis
- Customize ATS scoring criteria

---

## 📊 **Performance Optimization**

### **Backend Optimization**
- Database query optimization
- Caching strategies
- API response compression
- Rate limiting implementation

---

## 🔒 **Security Considerations**

### **Environment Variables**
- Never commit `.env` files to version control
- Use strong, unique API keys
- Rotate credentials regularly

### **API Security**
- Input validation and sanitization
- Rate limiting for API endpoints
- CORS configuration for production

---

## 🚀 **Deployment Options**

### **Local Development**
- Flask development server
- Local file-based database
- Development environment variables

### **Production Deployment**
- Gunicorn or uWSGI for Flask
- PostgreSQL or production Supabase
- Environment-specific configurations

---

## 📚 **Additional Resources**

### **Documentation**
- [Flask Documentation](https://flask.palletsprojects.com/)
- [Supabase Documentation](https://supabase.com/docs)
- [NLTK Documentation](https://www.nltk.org/)

---

## 🆘 **Getting Help**

If you encounter issues:
1. **Check Flask logs** (terminal running app.py)
2. **Verify .env file** has correct credentials
3. **Test individual components** using test files
4. **Check database connection** in Supabase dashboard

### **Common Error Messages**
- `ModuleNotFoundError`: Install missing packages
- `Environment variable not found`: Check .env file
- `Database connection failed`: Verify Supabase credentials

---

## 🎯 **Next Steps After Backend Setup**

1. **Test all API endpoints** thoroughly
2. **Implement additional features** (authentication, caching)
3. **Add more resume analysis** capabilities
4. **Deploy to production** environment
5. **Set up monitoring** and error tracking

---

## 📝 **Changelog**

### **Version 1.0.0**
- Initial release with basic internship management
- Resume analysis with AI-powered insights
- Complete API documentation
- Supabase database integration

---

**Happy Backend Development! 🚀**

Your PM Internship Portal backend should now provide a robust, scalable foundation with comprehensive API endpoints, efficient database operations, and powerful resume analysis capabilities.

---

*Last updated: December 2024*
*Version: 1.0.0*

---

**Note**: This guide focuses only on backend setup. For frontend integration, refer to the separate Frontend Setup Guide.
