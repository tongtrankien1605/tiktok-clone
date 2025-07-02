## tiktok-clone by Tống Trần Kiên

</br>

## 🏆 Đây là code base, mã nguồn này có thể được sử dụng để clone hoặc phát triển các ứng dụng lớn hơn

    - Mỗi lần truy cập, video được tải từ CDN jsDelivr (Content Delivery Network) mà không lưu trữ trong Service Worker
    giúp tối ưu hóa hiệu suất nhờ sử dụng CDN, và tối ưu bộ nhớ thiết bị.

    - Service Worker: Chỉ lưu trữ các dữ liệu tĩnh (HTML, CSS, v.v.) và không lưu dữ liệu động (video). Điều này giúp
    giảm dung lượng bộ nhớ cache vì chỉ lưu các tệp tĩnh có kích thước nhỏ.

    - Note 1: Video được lưu trữ trên CDN không tính băng thông cho GitHub Pages. Khi truy cập lại, video sẽ được 
    tải lại từ server CDN theo trình tự.

    - Note 2: Tuy nhiên CDN jsDelivr có cơ chế cache HTTP 7 ngày, Nên do đó có thể tận dụng và xem lại video từ cache HTTP
    mà không cần tải lại từ server CDN cho đến khi cache hết hạn ( sử dụng cache HTTP cho video )

    - Note 3: File videos.json hỗ trợ 3 loại: CDN jsDelivr, liên kết base GitHub (chứa /blob), và liên kết raw GitHub. 
    Có logic tự động chuyển đổi các liên kết base và raw thành liên kết CDN để tải dữ liệu với băng thông không giới hạn.

    - Note 4: Để thay đổi video đã tải lên GitHub. Xóa video cũ và thêm video mới ( phải trùng tên ) -> Commit thay đổi
    -> Xóa cache CDN tại: ( https://www.jsdelivr.com/tools/purge ) -> Update version -> Chờ khoảng 5-10p và done

    - Note 5: Sử dụng baseConfig và hostname để cấu hình BASE_URL cho các nền tảng như GitHub Pages, Netlify, Vercel, v.v.

    - Note 6: Sử dụng window.location.pathname ( HTML ) và self.registration.scope ( Service Worker ) để lấy pathname 
    làm basepath cho REPOSITORY_ROOT trên GitHub Pages và GitLab Pages.

    - Note 7: Cấu hình baseConfig để ánh xạ lấy basepath đối với các dịch vụ: Github ( github.io ), Gitlab ( gitlab.io ),
    Netlify ( netlify.app ), Vercel ( vercel.app ), Cloudflare Pages ( pages.dev ), Render ( onrender.com )

    - Note 8: GitHub Pages và GitLab Pages tự động cấu hình basepath thông qua URL ( sử dụng window.location.pathname ). 
    Các dịch vụ khác được ánh xạ thông qua baseConfig với các cặp key và basepath.

</br>

## 🫣 Các giới hạn được thu thập được trong quá trình tester

    - Giới hạn tải lên trực tiếp trên web GitHub: Tối đa 25 MB (Yowza, that’s a big file. Try again with a file smaller than 25MB)

    - Cảnh báo khi tải lên qua GitHub: Tệp vượt 50 MB (This is larger than GitHub's recommended maximum file size of 50.00 MB)

    - Giới hạn tải lên qua VS Code trên GitHub: Tối đa 100 MB (This exceeds GitHub's file size limit of 100.00 MB)

    - Giới hạn tệp trên CDN jsDelivr: Tối đa 20 MB (File size exceeded the configured limit of 20 MB)

</br>

## 💻 Giải thích các BASE_URL:

    const REPOSITORY_ROOT: Đường dẫn gốc của dự án, dùng để đăng ký Service Worker.
    ( ví dụ xây dựng trên github có repository là tiktok-clone => thì REPOSITORY_ROOT = "/tiktok-clone/" )

    const VIDEOS_JSON_URL: Đường dẫn đến file JSON chứa thông tin video như Title, URL, Desription, dayCreate
    ( ví dụ xây dựng trên github có repository là tiktok-clone => thì const VIDEOS_JSON_URL = `${REPOSITORY_ROOT}videos.json`; )

    const CACHE_NAME: Tên của Worker Service, lưu ý cần cập nhật ở cả file html & script. ( const CACHE_NAME = "service-worker-v1" )

</br>

## ❌ Cách xóa Local Storage, Cache Service Worker, Cache HTTP:

    Settings -> Privacy and security -> Delete browsing data -> Cached images and files : Xóa Cache HTTP
    ( Cài đặt -> Quyền riêng tư và bảo mật -> Xóa dữ liệu duyệt web -> Tệp và hình ảnh được lưu trong bộ nhớ đệm )

    F12 -> Application -> Local storage : xóa Local Storage

    F12 -> Application -> Cache storage : xóa Cache Service Worker

</br>
