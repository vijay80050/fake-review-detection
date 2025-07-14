# Fake Product Review Detection & Sentiment Analysis

A Django-based web application that detects fake product reviews and performs sentiment analysis on customer feedback using Natural Language Processing (NLP) techniques.

## 🎯 Project Overview

This project implements a comprehensive system for analyzing product reviews to:

- Detect potentially fake or fraudulent reviews
- Perform sentiment analysis on customer reviews
- Provide visual sentiment indicators with color-coded ratings
- Manage products, companies, and user reviews
- Generate sentiment-based insights for better business decisions

## ✨ Features

### Core Functionality

- **Sentiment Analysis**: Real-time sentiment analysis using TextBlob NLP library
- **Review Management**: Complete CRUD operations for product reviews
- **User Authentication**: Secure user registration and login system
- **Product Management**: Comprehensive product catalog with company associations
- **Order Management**: Full order tracking and status management
- **Visual Feedback**: Color-coded sentiment indicators

### Sentiment Classification

The system classifies reviews into 7 distinct sentiment categories:

- **Strongly Positive** (5.0) - Green (32, 229, 25)
- **Positive** (4.0) - Light Green (65, 244, 149)
- **Weakly Positive** (3.5) - Light Blue (65, 238, 244)
- **Neutral** (3.0) - Blue (24, 78, 229)
- **Weakly Negative** (2.5) - Light Red (249, 144, 144)
- **Negative** (2.0) - Pink (229, 24, 181)
- **Strongly Negative** (1.0) - Red (244, 65, 65)

## 🛠️ Technology Stack

### Backend

- **Framework**: Django 2.0
- **Database**: SQLite3 (development), MySQL (production)
- **NLP Library**: TextBlob 0.15.3
- **Text Processing**: NLTK 3.4.1

### Frontend

- **Templates**: Django HTML Templates
- **Styling**: CSS3 with custom themes
- **JavaScript**: jQuery for dynamic interactions
- **UI Components**: Font Awesome icons, Owl Carousel

### Data Visualization

- **Charts**: Matplotlib 3.0.3
- **Analysis**: NumPy 1.16.3 for numerical computations

## 📁 Project Structure

```text
fake_product_review_detection_sentiment_analysis/
├── fake_product_review_detection_sentiment_analysis/    # Main project directory
│   ├── settings.py                                      # Django settings
│   ├── urls.py                                         # URL configurations
│   └── utils.py                                        # Utility functions
├── products/                                           # Products app
│   ├── models.py                                       # Product models
│   ├── views.py                                        # Product views
│   ├── SentimentAnalysis.py                           # Core sentiment analysis
│   └── templates/                                      # Product templates
├── users/                                              # User management app
├── company/                                            # Company management app
├── type/                                               # Product type management
├── test/                                               # Testing app
├── pages/                                              # Static pages app
├── templates/                                          # Global templates
│   ├── base.html                                       # Base template
│   ├── index.html                                      # Home page
│   ├── about.html                                      # About page
│   └── contact.html                                    # Contact page
├── assets/                                             # Static assets
│   ├── css/                                           # Stylesheets
│   ├── js/                                            # JavaScript files
│   ├── images/                                        # Image assets
│   └── fonts/                                         # Font files
├── media/                                              # User uploaded files
├── requirements.txt                                    # Python dependencies
├── manage.py                                           # Django management script
└── db.sqlite3                                         # SQLite database
```

## ⚡ Quick Start (Localhost)

To quickly run this project on your local machine:

1. **Prerequisites**: Make sure you have Python 3.6+ and pip installed
2. **Clone & Navigate**:
   ```bash
   git clone <repository-url>
   cd "Fake Product Review Detection Sentiment Analysis/fake_product_review_detection_sentiment_analysis"
   ```
3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   python -c "import nltk; nltk.download('punkt'); nltk.download('brown')"
   ```
4. **Setup Database**:
   ```bash
   python manage.py migrate
   python manage.py createsuperuser  # Create admin account
   ```
5. **Run Server**:
   ```bash
   python manage.py runserver
   ```
6. **Access Application**:
   - **Main Site**: http://localhost:8000 or http://127.0.0.1:8000
   - **Admin Panel**: http://localhost:8000/admin
   - **Login**: Use the superuser credentials you created

> **Note**: The server will automatically reload when you make changes to the code.

## 🚀 Getting Started

### Prerequisites

- Python 3.6+
- pip (Python package manager)
- Git

### Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd fake_product_review_detection_sentiment_analysis
   ```

2. **Create a virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   cd fake_product_review_detection_sentiment_analysis
   pip install -r requirements.txt
   ```

4. **Download NLTK data** (required for TextBlob)

   ```python
   python -c "import nltk; nltk.download('punkt'); nltk.download('brown')"
   ```

5. **Set up the database**

   ```bash
   python manage.py migrate
   ```

6. **Load sample data** (optional)

   ```bash
   # Import the provided SQL dump if needed
   python manage.py dbshell < ../fake_product_review_detection_sentiment_analysis.sql
   ```

7. **Create a superuser**

   ```bash
   python manage.py createsuperuser
   ```

8. **Run the development server**

   ```bash
   python manage.py runserver
   ```

9. **Access the application on localhost**
   - **Main Application**: Open your browser and go to `http://localhost:8000/` or `http://127.0.0.1:8000/`
   - **Admin Panel**: `http://localhost:8000/admin/` or `http://127.0.0.1:8000/admin/`
   - **API Endpoints**: All endpoints will be available on `http://localhost:8000/`

> **Localhost Info**: The Django development server runs on port 8000 by default. If you need to change the port, use: `python manage.py runserver 8080` (replace 8080 with your desired port)

## 💡 Usage

### For End Users

1. **Register/Login**: Create an account or login to access the system
2. **Browse Products**: View available products with detailed descriptions
3. **Submit Reviews**: Add reviews with ratings for products you've purchased
4. **View Sentiment**: See real-time sentiment analysis of your reviews
5. **Track Orders**: Monitor your order status and history

### For Administrators

1. **Product Management**: Add, edit, and manage product catalogs
2. **Review Monitoring**: View all reviews with sentiment analysis
3. **User Management**: Manage user accounts and permissions
4. **Analytics**: Access sentiment trends and review analytics

## 🔧 Troubleshooting Localhost Setup

### Common Issues and Solutions

1. **Port 8000 already in use**:
   ```bash
   # Use a different port
   python manage.py runserver 8080
   # Or find and kill the process using port 8000
   netstat -ano | findstr :8000  # Windows
   lsof -ti:8000 | xargs kill -9  # macOS/Linux
   ```

2. **Module not found errors**:
   ```bash
   # Make sure virtual environment is activated
   pip install -r requirements.txt
   # Verify Python path
   python -c "import sys; print(sys.path)"
   ```

3. **Database errors**:
   ```bash
   # Reset database
   python manage.py flush
   python manage.py migrate
   python manage.py createsuperuser
   ```

4. **NLTK data missing**:
   ```bash
   python -c "import nltk; nltk.download('all')"
   ```

5. **Permission errors on Windows**:
   - Run Command Prompt as Administrator
   - Or use: `python -m pip install --user -r requirements.txt`

### Development Server Features

- **Auto-reload**: The server automatically restarts when you modify Python files
- **Static files**: Served automatically in development mode
- **Debug mode**: Detailed error pages (set `DEBUG = True` in settings.py)
- **Database**: SQLite database file created automatically

## 🔍 Sentiment Analysis Details

The sentiment analysis engine uses TextBlob's polarity scoring:

- **Polarity Range**: -1.0 (most negative) to 1.0 (most positive)
- **Classification Logic**:

  ```python
  if polarity == 0: return "Neutral" (3.0)
  elif 0 < polarity <= 0.3: return "Weakly Positive" (3.5)
  elif 0.3 < polarity <= 0.6: return "Positive" (4.0)
  elif 0.6 < polarity <= 1.0: return "Strongly Positive" (5.0)
  elif -0.3 < polarity <= 0: return "Weakly Negative" (2.5)
  elif -0.6 < polarity <= -0.3: return "Negative" (2.0)
  elif -1.0 <= polarity <= -0.6: return "Strongly Negative" (1.0)
  ```

## 📊 Database Schema

### Key Tables

- **products_product**: Product information and inventory
- **comment**: User reviews with sentiment analysis results
- **users_user**: User account management
- **company**: Company/brand information
- **order** & **order_item**: Order management system
- **django_session**: Session management

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🔒 Security Considerations

- Change the `SECRET_KEY` in production
- Set `DEBUG = False` in production
- Configure proper database settings for production
- Implement HTTPS in production environments
- Regular security updates for dependencies

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- TextBlob library for sentiment analysis
- Django framework for web development
- NLTK for natural language processing
- Bootstrap and jQuery for frontend components

## 📞 Support

For support and questions:

- Create an issue in the repository
- Contact the development team
- Check the documentation in the `docs/` directory

---

**Note**: This project is for educational and research purposes. Please ensure compliance with data privacy regulations when using in production environments.
