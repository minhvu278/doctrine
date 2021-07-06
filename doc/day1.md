## Install 
    - composer create-project laravel/laravel example-app

## Configuration
    - Tất cả các cấu hình trong PHP đều nằm trong thư mục config 
    1. Cấu hình môi trường 
        - Tệp .env chứa 1 số giá trị về việc ứng dụng chạy local hay serve 
        - Có thể bị ghi đè bởi biến môi trường như : server-level system-level
        - Có thể truy cập dễ dàng các cấu hình bằng cách sử dụng global config, các giá trị có thể truy cập bằng dấu . 
                VD: 
                    $value = config('app.timezone');

                    config(['app.timezone' => 'America/Chicago']);

    2. Config Caching
        - Để tăng tốc ứng dụng, nên lưu tất cả các tệp cấu hình vào 1 tệp duy nhất. Sử dụng : config:cache 
        - Câu lệnh: php artisan config:cache 

    3. Debug mode
        - debug trong config/app.php xác định thông tin về lỗi được hiển thị cho người dùng 
        - APP_DEBUG trong env = true/false
    
    4. Maintenance Mode
    



## Routing
    1. Khái niệm cơ bản
        - Được lưu trong thư mục routes 
        - routes/web.php : Xác định đường dẫn trên trình duyệt 
        - Dùng được các method : get, post, put, patch, delete, options 
        - Có thể dùng match để gộp các method: VD: 
                                                    Route::match(['get', 'post'], '/', function(){

                                                    })
            +. Hoặc dùng any để sử dụng tất cả các phương thức: 
                     VD: 
                        Route::any('/', function(){

                        })
    2. Dependency Injection 
                Route::get('/users', function(Request $request){

                })

    3. CSRF
        - Trong form phải có @csrf nếu không sẽ bị từ chối 

    4. Route redirect 
        - Sử dụng Route::redirect :             Route::redirect('/here', '/there')
        - Mặc định nó sẽ trả về 302, ta có thể thay đổi bằng cách truyền tham số thứ 3 
                    VD: 
                        Route::redirect('/here', '/there', 301)
        - Dùng Route::permanentRedirect -> Trả về 301 
    
    5. View Routes 
        - Nếu đường dẫn chỉ cần trả về view thì sử dụng luôn Route::view
                VD: 
                    Route::view('/welcome', 'welcome')

    6. Route Parameters
        6.1. Required Parameters
            - Lấy id: 
                +. Route::get('/user/{id}', function ($id){
                    return 'User ' . $id
                })
            - Có thể lấy nhiều tham số: 
                Route::get('/posts/{post}/comments/{comment}', function ($postId, $commentId){

                })
        6.2. Optional Parameters
            - Có thể chỉ định 1 tham số trên URL bằng cách đặt ?  sau tham số : 
                            VD: 
                                Route::get('/user/{name?}, function ($name = 'Vu Dz'){
                                    return $name;
                                })
        6.3. Regular Expression Constraints
            - Có thể giới hạn tham số trên URL sử dụng keyword  where('regular')
        
        6.4. Name Route 
        


