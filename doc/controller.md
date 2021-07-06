## Controller
    1. Tạo controller💖
        - php artisan make:controller VudzController --resource : Sinh ra các CURD trong controller 

    2. Khai báo route cho controller💖
        Route::resource('vu', 'VudzController') : Khai báo tất cả các action trong VudzController 
        - Có thể khai báo nhiều resource controller 
            Route::resources([
                'vudz' => 'VudzController',
                'anhvu' => 'AnhvuController'
            ])

    3. Giả method💖
        - Trong HTML không có method PUT PATCH DELETE nên ta dùng @method để gán các method vào 
            @method('PUT')

    4. Sử dụng action chỉ định💖
        - only(['']) : Chỉ sử dụng action truyền vào bên trong
        - except(['']) : Loại trừ các action truyền vào bên trong 

    5. Có thể ghi đè name route💖
        - Có thể thay đổi tên mặc định của resource bằng cách
            Route::resource('vudz', 'VudzController')->names([
                'create' => 'vudz.build'
            ])
    
     