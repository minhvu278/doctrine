## View
    - Nằm trong thư mục resource/views


## Blade template engine
    1. Template engine 
        - Là 1 bố cục chung cho all các trang có sử dụng lại những thành phần giống nhau mà không phải viết lại toàn bộ ❤
        - Có tác dụng dọn sạch những đoạn code PHP nằm trong View 
    2. Blade template🦊
        - File phải dưới dạng xxx.blade.php
        - Cú pháp trong Blade template : Để hiển thị dữ liệu dùng {{$x}} (file blade sẽ tự build ra <?php echo $name ?>)
        - Hiển thị dữ liệu tồn tại : {{isset($name) ? $name : 'Hello world! }} (Có thể viết rút gọn {{$name or 'Default'}}) 😁😁
        - Không chấp nhận kiểu comment  // {{$name}}
    3. Cấu trúc câu lệnh if🦊
        @if (true)
            {{'is true !'}}
        @else
            {{'is false !'}}
        @endif
    4. Câu lệnh for 🦊
        @for ($i = 0; $i < 10; $i++>)
            Giá trị hiện tại {{$i}}
        @endfor
    5. Foreach🦊
        @foreach($users as $user)
            <p> DAy la user {{$user->id}} </p>>
    6. While 🦊
        @while (true)
            <Toi dang lap mai mai >
        @endwhile
    😉😉😉😉😉😉😉😉😉😉😉😉

    7. Kế thừa
        - Tránh bị lặp lại code 😊
        - Cú pháp: @include('example', ['name1' = $name])
    
    8. Layout 🦢
        - Thiết kế layout giúp tận dụng tối đa sức mạnh của blade
        - 


    