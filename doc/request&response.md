## Request
    1. Là gì
        - Là yêu cầu mà client gửi đến server
        - Trong laravel thì là 1 object chứa các thông tin liên quan đến HTTP request hiện tại, dựa vào đó ta có thể lấy được các thông tin như input, cookie, file,...
    2. Tương tác với request
        - Mặc định request đã đc binding vào service container nên khi dùng chỉ cần binding vào argument khi cần 
    3. Các phương thức hỗ trợ của request
        $request->path() : Trả về thông tin đường dẫn\
        $request->ís() : Kiểm tra đường dẫn request có khớp với 1 mẫu hay không. Dùng * để khớp tất cả
        $request->method() : Trả về hành động là GET hay POST(Có thể sử dụng isMethod để xác định hành động là get hay post)
        $request->header() : Trả về các thông tin header như: thông tin dữ liệu cookie, host yêu cầu,...       
    4. Lấy thông tin từ form trong request 😉
        4.1, Nhận giá trị từ input
            - Lấy qua Illuminate\Http\Request :    $name = $request->input('email');
            - Có thể truyền giá trị mặc định vào đối số thứ 2, nếu giá trị trong input k có trong request thì sẽ đc lấy
                $name = $request->input('email','email@gmail.com');
            - Đối với dữ liệu trên form là mảng dữ liệu, sử dụng . để truy cập vào mảng 
                $names = $request->input('categories.*.name');
        4.2. Nhận giá trị input từ JSON
            - Có thể truy xuất dữ liệu thông qua hàm input
                $name = $request->input('categories.name');
            - Sử dụng has() để kiểm tra input có tồn tại k
                if($request->has('email')){
                    
                }
    