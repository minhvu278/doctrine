## Model
    1. Tạo model
        - php artisan make:model News (--migration) : Thêm migration thì sẽ tạo luôn migration có tên là news
    2. Khai báo thông số tùy chỉnh 
        - Mỗi model ứng với 1 bảng trong CSDL. Khai báo sử dụng model : 
            protected $table = 'tableName';
    3. Lọc dữ liệu trong model
        - Sử dụng fillable để điều chỉnh các cột cần sử dụng
            protected $fillable = ['cot1', 'cot2',...];

    4. Khai báo timestamps
        - Cung cấp tùy biến sử dụng timestamps hay không
            $public $timestamp = true;
            