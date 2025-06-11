## 🚀 tiktok-clone : Lướt video tương tự tiktok, có xây dựng các Base_URL để chủ động thay đổi đường dẫn mà không cần sửa logic xử lý 

</br>

## 🌐 Truy cập để xem  [TẠI ĐÂY](https://tongtrankien1605.github.io/tiktok-clone) nhé !

</br>

## 🏆 Đây là code base, có thể dùng để xây dựng phát triển thêm các chương trình mới
            - Mỗi lần truy cập sẽ tải dữ liệu video từ ( server lưu trữ video ) để xem, và sẽ được lưu vào cache Service Worker 
            để tải nhanh khi lướt xem lại những video cũ mà không cần tải từ server
            
            - Service Worker chỉ cache các dữ liệu tĩnh ( html, css,... ) và không cache dữ liệu động ( video,... ) -> Nhiều video
            cũng không gây tốn cache vì chỉ cache dữ liệu tĩnh có dung lượng nhỏ

            - VD: Khi lưu trữ video bằng cdn web khác thì băng thông tính cho web đó. Do đó, sau khi thoát ra, và khi truy cập lại
            sẽ lại tải từ server để xem theo trình tự như vậy, video được tải từ cdn của web lưu video

</br>

## 💻 Giải thích các BASE_URL:

            - BASE_URL_VIDEO: Đường dẫn gốc đến thư mục chứa video. 
            ( ví dụ https://cdn.anh.moe/s9/1VsTi103.mp4 => thì BASE_URL_VIDEO = "https://cdn.anh.moe/s9/" )

            - REPOSITORY_PROJECT_ROOT: Đường dẫn gốc của dự án, dùng để đăng ký Service Worker.
            ( ví dụ xây dựng trên github có repository là tiktok-clone => thì REPOSITORY_PROJECT_ROOT = "/tiktok-clone/" )
              
            - VIDEOS_JSON_URL: Đường dẫn đến file JSON chứa thông tin video như Title, URL, desription.
            ( ví dụ xây dựng trên github có repository là tiktok-clone => thì VIDEOS_JSON_URL = "/tiktok-clone/videos.json" )
            
</br> 

## ❌ Cách xóa Local Storage, Cache Service Worker, Cache HTTP:

            - Settings -> Privacy and security -> Delete browsing data -> Cached images and files : Xóa Cache HTTP
            ( Cài đặt -> Quyền riêng tư và bảo mật -> Xóa dữ liệu duyệt web -> Tệp và hình ảnh được lưu trong bộ nhớ đệm )

            - F12 -> Application -> Local storage : xóa Local Storage

            - F12 -> Application -> Cache storage : xóa Cache Service Worker
