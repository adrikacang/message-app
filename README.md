# 1. Clone Repository
bash# Clone dari GitHub
git clone https://github.com/username/message-app.git

Masuk ke folder project
cd message-app

# 2. Install Dependencies
bash# Install PHP dependencies
composer install

# Install Node.js dependencies (jika menggunakan Laravel Mix/Vite)
npm install

# 3. Setup Environment
bash# Copy environment file
cp .env.example .env

# Generate application key
php artisan key:generate

# 4. Edit File .env
Edit file .env sesuai kebutuhan:
envAPP_NAME="Message App"
APP_ENV=local
APP_KEY=base64:xxxxx
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

# Untuk SQLite
DB_CONNECTION=sqlite

# Untuk MySQL (jika menggunakan XAMPP)
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=message_app
DB_USERNAME=root
DB_PASSWORD=

# 5. Setup Database
Untuk SQLite:
bash# Buat file database kosong
touch database/database.sqlite

# Jalankan migration
php artisan migrate
Untuk MySQL:
bash# Buat database di phpMyAdmin dengan nama 'message_app'
# Kemudian jalankan migration
php artisan migrate

# 7. Build Assets (jika diperlukan)
bash# Compile assets
npm run build

# Atau untuk development
npm run dev

# 8. Set Permissions (untuk Linux/Mac)
bash# Set permissions untuk storage dan cache
chmod -R 775 storage
chmod -R 775 bootstrap/cache

# 9. Test Aplikasi
bash# Start development server
php artisan serve
