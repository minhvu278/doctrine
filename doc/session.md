## Session
    - Đóng vai trò lưu trữ thông tin request để các request tiếp theo có thể truy xuất thông tin được
    - Có thể sử dụng session qua: database, file, Redis,...

    1. Cấu hình ⚙
        - Trong file config/session.php
        - Các thông số trong config/session.php :
            +. lifetime: Thời gian sống của session (tính bằng đơn vị phút)
            +. expire_on_close: Xóa khi người dùng đóng trình duyệt
            +. encrypt: Có mã hóa session trước khi lưu trữ không ?
            +. files : path sẽ lưu trữ session nếu session driver là file
            +. cookie : Cookie key name để lưu trữ indentify session
        
    2. Yêu cầu cho từng session
        - Database: Nếu sử dụng drive là database thì cần phải tạo 1 table để lưu trữ thông tin session 
            +. Chạy lệnh : php artisan session:table   -> sau đó migrate vào db
        
    3. Tương tác với session
        - Có 2 cách lấy session: 
            +. Thông qua session helper
                VD: 
                    public function show (Request $request, $id){
                        $value = $request->session()->get('key');
                        || $value = session('key')
                        || $value = session()->get('key')
                        || $value = Session::get('key')
                    }
            +. Sử dụng Request 
        - Để lấy dữ liệu dùng phương thức get
        - Có thể truyền tham số thứ 2 làm giá trị mặc định khi key không tồn tại
        - Lấy tất cả session : $vu = Session::all()
        - Kiểm tra tồn tại dùng phương thức has 
            if( $request->session()->has('users')){

            }
        - Nếu chỉ cần kiểm tra session có tồn tại không mà k cần quan tâm giá trị thì dùng ->exists('')

    4. Lưu session 💖
        - Sử dụng phương thức put :  session()->put($key, $value)
            VD:    
                $session = Session::put('cart.products', [['id' => 1, 'item'=> 1]]);
            


