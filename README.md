## 🚀 tiktok-clone : Lướt video tương tự tiktok, có xây dựng các Base_URL để chủ động thay đổi đường dẫn mà không cần sửa logic xử lý 

</br>

## 🌐 Truy cập để xem  [TẠI ĐÂY](https://tongtrankien1605.github.io/tiktok-clone) nhé !

</br>

## 🏆 Đây là code base, có thể sử dụng để xây dựng phát triển thêm các chương trình lớn hơn
            - Mỗi lần truy cập sẽ tải dữ liệu video từ ( server lưu trữ video ) để xem, và sẽ được lưu vào cache Service Worker 
            để tải nhanh khi lướt xem lại những video cũ mà không cần tải từ server
            
            - Service Worker chỉ cache các dữ liệu tĩnh ( html, css,... ) và không cache dữ liệu động ( video,... ) -> Nhiều video
            cũng không gây tốn cache vì chỉ cache dữ liệu tĩnh có dung lượng nhỏ

            - VD: Khi lưu trữ video bằng cdn web khác thì băng thông tính cho web đó. Do đó, sau khi thoát ra, và khi truy cập lại
            sẽ lại tải từ server để xem theo trình tự như vậy, video được tải từ cdn của web lưu video

            - Nếu logic không cache video mà vẫn thấy cache được sử dụng để phát video mà không tải từ server, có thể là do video
            được lấy từ cache trình duyệt, còn được gọi là cache HTTP

            - Bản Final Code on 15/06/2025: Sử dụng đường dẫn tuyệt đối cho URL video trong videos.json , do đó có thể dùng được 
            nhiều nguồn video: CDN website bên thứ 3, link raw github,....

</br>

## 💻 Giải thích các BASE_URL:

            - REPOSITORY_PROJECT_ROOT: Đường dẫn gốc của dự án, dùng để đăng ký Service Worker.
            ( ví dụ xây dựng trên github có repository là tiktok-clone => thì REPOSITORY_PROJECT_ROOT = "/tiktok-clone/" )
              
            - VIDEOS_JSON_URL: Đường dẫn đến file JSON chứa thông tin video như Title, URL, desription.
            ( ví dụ xây dựng trên github có repository là tiktok-clone => thì VIDEOS_JSON_URL = "/tiktok-clone/videos.json" )

            - CACHE_NAME: Tên Cache của Worker Service, lưu ý cần cập nhật ở cả file html & script. ( const CACHE_NAME = "tiktok-clone-v1" )
            
</br> 

## ❌ Cách xóa Local Storage, Cache Service Worker, Cache HTTP:

            - Settings -> Privacy and security -> Delete browsing data -> Cached images and files : Xóa Cache HTTP
            ( Cài đặt -> Quyền riêng tư và bảo mật -> Xóa dữ liệu duyệt web -> Tệp và hình ảnh được lưu trong bộ nhớ đệm )

            - F12 -> Application -> Local storage : xóa Local Storage

            - F12 -> Application -> Cache storage : xóa Cache Service Worker
