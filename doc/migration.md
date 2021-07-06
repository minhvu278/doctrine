## Migration
    - Cho phép định nghĩa nội dung, cập nhật các bảng trong CSDL 
    - Có thể sử dụng trên nhiều loại CSDL khác nhau mà k cần chỉnh code theo CSDL
    - Phải kết nối database
    - Nằm trong thư mục App\database\migrtions

    1. Tạo migration
        php artisan make:migration create_posts_table --create=posts

    2. Rollback
        - php artisan migrate:refresh : Thực hiện down xong up
        - php artisan migrate:rollback -step=n : Thực hiện down() với số lần muốn rollback 
    3. Sửa đổi cột
        - Muốn giá trị table là null hoặc not null, sử dụng các modifier
            Schema::table('users', function($table) {
                $table->string('address')->nullable();
            });
    4. Đổi tên cột
        - Cài thư viện doctrine 
        - Đổi tên cột
            $table->renameColumn('from', 'to')
        - Giới hạn giá trị kiểu dữ liệu của cột
            $table->string('name', 50)->nullable()->change();
    5. Khóa ngoại
        - Ràng buộc cho 2 bảng 
            Schema::table('posts' function ($table) {
                $table->integer('user_id')->unsigned();
                $table->foreign('user_id)->references('id')->on('users');
            })
        - Drop 1 foreign key : $table->dropForeign('id_foreign')
        - Quy tac dat ten foreign
            <ten_table>_<ten_khoa_ngoai>_foreign
        - Kích hoạt hoặc bỏ kích hoạt việc sử dụng foreign key constraint trong migrate:
            Schema::enableForeignKeyConstraints();
            Schema::disableForeignKeyConstraints();
