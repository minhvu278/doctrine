## Eloquent Model 
    1. ORM là gì 
        - Object Relational Mapping là kĩ thuật để chuyển đổi dữ liệu từ không hướng đối tượng -> hướng đối tượng😉
    2. Eloquent Model
        - Eloquent ORM là thư viện ORM cài đặt kèm với LRV, cung cấp các phương thức truy xuất dữ liệu đơn giản👌
        - Với mỗi model ta cần quan tâm đến 4 hành động CRUD ✔
    3. Định nghĩa Model và thiết lập cơ bản
        - Tạo model : php artisan make:model Post (--migration || -m) tạo luôn cả migration😎
        - Tên bảng: Nếu đặt tên là Post thì laravel sẽ mapping với posts 😍
        - Khóa chính : Mặc định là id nhưng nếu muốn thay đổi thì có thể khai báo qua biến $primaryKey: protected $primaryKey = 'id_post';
        - Timestamps: Khi tạo sẽ có 2 trường created_at &update khi thêm bản ghi vào table nó sẽ tự động cập nhật(Không muốn tự cn->false)
        - Kết nối DB: Mặc định DB khai báo trong .env nhưng nếu muốn model kết nối đến CSDL nào đó thì set :
            protected $connection = 'connection-name';😎
    4. Lấy dữ liệu từ DB
        - Tất cả : dùng all()       VD:  $flights = App\Post::all();
        - Thêm ràng buộc: Cho những trường hợp không cần nhất thiết lấy tất cả(Sẽ làm giảm hiệu năng)😁
            VD: 
                $post = $Post::where('published', true)
                            ->orderBy('title', DESC)
                            ->take(5)
                            ->get();
        - Chunk : Xử lý với tập dữ liệu lớn 

