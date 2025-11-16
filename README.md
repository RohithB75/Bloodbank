# Blood Bank Donor Management System (BBDMS)

A comprehensive web-based application for managing blood donors and facilitating blood donation processes. This system helps blood banks and organizations efficiently manage donor information, search for donors by blood group, and handle contact queries.

## Features

### Public Features
- **Home Page**: Welcome page with information about blood donation
- **Become a Donor**: Registration form for new blood donors
- **Search Donors**: Search and filter donors by blood group
- **Contact Us**: Contact form for inquiries
- **Dynamic Pages**: CMS-like functionality for managing content pages

### Admin Panel Features
- **Dashboard**: Overview of system statistics
- **Donor Management**: 
  - Add new donors
  - View donor list
  - Manage donor records
  - Download donor records
- **Blood Group Management**: Add and manage blood groups
- **Contact Query Management**: View and manage contact inquiries
- **Page Management**: Manage dynamic content pages (About Us, Why Become Donor, etc.)
- **Contact Information**: Update organization contact details
- **Change Password**: Admin password management

## Technology Stack

- **Backend**: PHP
- **Database**: MySQL/MariaDB
- **Frontend**: 
  - Bootstrap 4
  - jQuery
  - Font Awesome
  - DataTables (for admin tables)
  - Chart.js (for dashboard charts)
- **Server Requirements**: 
  - PHP 7.4 or higher
  - MySQL 5.7+ / MariaDB 10.4+
  - Apache/Nginx web server

## Installation

### Prerequisites
- Web server (Apache/Nginx)
- PHP 7.4 or higher
- MySQL/MariaDB database server
- phpMyAdmin (optional, for database management)

### Step-by-Step Installation

1. **Clone or Download the Project**
   ```bash
   git clone <repository-url>
   cd bloodbank
   ```

2. **Database Setup**
   - Create a new MySQL database named `bbdms`
   - Import the SQL file located at `bloodbank/sqlfile/bbdms.sql`
   - You can use phpMyAdmin or command line:
     ```bash
     mysql -u root -p bbdms < bloodbank/sqlfile/bbdms.sql
     ```

3. **Configure Database Connection**
   - Edit `bloodbank/bbdms/includes/config.php`
   - Edit `bloodbank/bbdms/admin/includes/config.php`
   - Update the following constants:
     ```php
     define('DB_HOST','localhost');
     define('DB_USER','root');
     define('DB_PASS','your_password');
     define('DB_NAME','bbdms');
     ```

4. **Web Server Configuration**
   - Place the project in your web server's document root
   - For Apache: Place in `htdocs` or `www` directory
   - For XAMPP: Place in `C:\xampp\htdocs\bloodbank`
   - For WAMP: Place in `C:\wamp64\www\bloodbank`

5. **Access the Application**
   - Public site: `http://localhost/bloodbank/bloodbank/bbdms/`
   - Admin panel: `http://localhost/bloodbank/bloodbank/bbdms/admin/`

## Default Login Credentials

**Admin Panel:**
- Username: `admin`
- Password: `admin123` (MD5 hash: `25f9e794323b453885f5181f1b624d0b`)

> **Security Note**: Change the default password immediately after first login!

## Project Structure

```
bloodbank/
├── bloodbank/
│   ├── bbdms/
│   │   ├── admin/              # Admin panel
│   │   │   ├── includes/       # Configuration and header files
│   │   │   ├── css/            # Admin stylesheets
│   │   │   ├── js/             # Admin JavaScript files
│   │   │   ├── fonts/          # Font files
│   │   │   ├── img/            # Admin images
│   │   │   └── *.php           # Admin pages
│   │   ├── includes/           # Public site includes
│   │   ├── css/                # Public site styles
│   │   ├── js/                 # Public site scripts
│   │   ├── images/             # Public site images
│   │   ├── vendor/             # Third-party libraries
│   │   ├── mail/               # Email handling
│   │   └── *.php               # Public pages
│   └── sqlfile/
│       └── bbdms.sql           # Database schema and data
└── README.md
```

## Database Schema

The system uses the following main tables:

- **admin**: Admin user credentials
- **tblblooddonars**: Donor information
- **tblbloodgroup**: Available blood groups
- **tblcontactusinfo**: Organization contact information
- **tblcontactusquery**: Contact form submissions
- **tblpages**: Dynamic page content

## Usage

### For Donors
1. Visit the public website
2. Click "Become a Donor" to register
3. Fill in your details (Name, Mobile, Email, Gender, Age, Blood Group, Address)
4. Submit the form
5. Your registration will be reviewed by admin

### For Administrators
1. Login to the admin panel
2. View dashboard for system overview
3. Manage donors: Add, view, edit, or download donor records
4. Manage blood groups: Add new blood groups as needed
5. Handle contact queries from the public
6. Update contact information and manage pages

### Searching for Donors
1. Use the "Search Donor" feature on the public site
2. Select a blood group
3. View available donors with their contact information

## Features in Detail

### Donor Registration
- Full name, mobile number, email
- Gender and age
- Blood group selection
- Address and optional message
- Status management (active/inactive)

### Admin Dashboard
- Statistics overview
- Charts and graphs
- Quick access to all management features

### Blood Group Management
- Support for all standard blood groups (A+, A-, B+, B-, AB+, AB-, O+, O-)
- Easy addition of new blood groups

## Security Considerations

- **Change Default Password**: Immediately change the admin password after installation
- **Database Security**: Use strong database credentials
- **File Permissions**: Set appropriate file permissions on production servers
- **Input Validation**: The system includes basic validation; consider adding more robust validation for production use
- **SQL Injection**: Uses PDO prepared statements for database queries
- **XSS Protection**: Uses `htmlentities()` for output escaping

## Troubleshooting

### Database Connection Error
- Verify database credentials in `config.php` files
- Ensure MySQL service is running
- Check database name matches (`bbdms`)

### Page Not Found / 404 Errors
- Verify web server is running
- Check file paths are correct
- Ensure `.htaccess` is configured (if using Apache)

### Admin Login Issues
- Verify default credentials
- Check database has admin user inserted
- Clear browser cache and cookies

## Development

### Adding New Features
- Follow existing code structure
- Use PDO for database operations
- Maintain consistent styling with Bootstrap
- Test thoroughly before deployment

### Customization
- Modify CSS files in respective `css/` directories
- Update images in `images/` or `img/` directories
- Edit PHP files for functionality changes

## License

This project appears to be open-source. Please check for specific license information.

## Support

For issues, questions, or contributions:
- Review the code structure
- Check database configuration
- Verify server requirements

## Contributing

Contributions are welcome! Please ensure:
- Code follows existing style
- Database changes include migration scripts
- New features are tested
- Documentation is updated

## Version History

- **Version 1.0** (2020): Initial release with core functionality

---

**Note**: This is a PHP-based web application. Ensure your server environment meets the requirements before installation.
