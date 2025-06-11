## 🚀 tiktok-clone : Lướt video tương tự tiktok, có xây dựng các Base_URL để chủ động thay đổi đường dẫn mà không cần sửa logic xử lý 

</br>

## 🌐 Truy cập để xem  [TẠI ĐÂY](https://tongtrankien1605.github.io/tiktok-clone) nhé !

</br>

## 🏆 Đây là code base, có thể dùng để xây dựng phát triển thêm các chương trình mới
 **👉 Mỗi lần truy cập, xem video sẽ lưu vào cache để lướt lại không cần tải từ server. Mỗi lần thoát ra và truy cập thì tiến trình lặp lại**

</br>

## 💻 Giải thích các BASE_URL:

            - BASE_URL_VIDEO: Đường dẫn gốc đến thư mục chứa video. 
            ( ví dụ https://cdn.anh.moe/s9/1VsTi103.mp4 => thì BASE_URL_VIDEO = "https://cdn.anh.moe/s9/" )

            - REPOSITORY_PROJECT_ROOT: Đường dẫn gốc của dự án, dùng để đăng ký Service Worker.
            ( ví dụ xây dựng trên github có repository là tiktok-clone => thì REPOSITORY_PROJECT_ROOT = "/tiktok-clone/" )
              
            - VIDEOS_JSON_URL: Đường dẫn đến file JSON chứa thông tin video như Title, URL, desription.
            ( ví dụ xây dựng trên github có repository là tiktok-clone => thì VIDEOS_JSON_URL = "/tiktok-clone/videos.json" )
            
