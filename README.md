<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8"> <!-- mã hóa ký tự, đảm bảo hiển thị tiếng Việt đúng -->
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no" />
    <!-- viewport để trang hiển thị tốt trên thiết bị di động -->
    <title>Chúc mừng Ngày Nhà giáo Việt Nam 20/11</title> <!-- tiêu đề trang, hiển thị trên tab trình duyệt -->
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600;700&family=Pacifico&display=swap"
        rel="stylesheet"> <!-- import font từ Google Fonts dùng trong CSS -->
    <style>
        /* Toàn bộ phần CSS được đặt trong thẻ <style> để tệp dễ chia sẻ - có thể tách ra file .css nếu cần */

        * { /* selector universal áp dụng cho tất cả phần tử */
            margin: 0; /* bỏ margin mặc định của trình duyệt */
            padding: 0; /* bỏ padding mặc định */
            box-sizing: border-box; /* khiến padding và border được tính vào kích thước phần tử */
        }

        body {
            min-height: 100vh; /* chiều cao tối thiểu bằng viewport height, giữ layout cao đầy đủ */
            display: flex; /* dùng flexbox để căn giữa nội dung theo chiều dọc/nguồn */
            flex-direction: column; /* sắp xếp con theo cột */
            align-items: center; /* canh giữa ngang */
            justify-content: flex-start; /* bắt đầu từ trên */
            padding-top: 30px; /* khoảng cách trên để không chạm sát cạnh */
            /* subtle two-stop gradient for a gentle background */
            background: linear-gradient(135deg, #ffffff 0%, #f7f9ff 100%); /* nền gradient nhẹ */
            font-family: 'Quicksand', sans-serif; /* font mặc định cho body */
            overflow-x: hidden; /* ẩn tràn ngang để tránh thanh cuộn ngang */
            position: relative; /* cần cho body::before có vị trí tương đối */
        }

        body::before { /* pseudo-element dùng để tạo các gradient hình tròn mờ làm họa tiết nền */
            content: ""; /* cần để pseudo-element xuất hiện */
            position: absolute; /* đặt chồng lên body */
            inset: 0; /* top/right/bottom/left = 0, chiếm toàn bộ body */
            background-image: /* hai radial-gradient chồng lên nhau tạo hiệu ứng vệt sáng */
                radial-gradient(circle at 20% 80%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
                /* radial-gradient ở góc trái-dưới */
                radial-gradient(circle at 80% 20%, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
                /* radial-gradient ở góc phải-trên */
            pointer-events: none; /* cho phép click qua layer này, không chặn tương tác */
        }

        .intro { /* lớp chứa màn hình chào mời (intro) */
            display: flex;
            flex-direction: column;
            justify-content: center; /* căn giữa theo chiều dọc */
            align-items: center; /* căn giữa theo chiều ngang */
            cursor: pointer; /* gợi ý có thể chạm/click */
            padding: 20px; /* khoảng cách phía trong */
            height: calc(100vh - 40px); /* chiếm gần hết chiều cao cửa sổ */
            overflow-y: hidden; /* ẩn cuộn dọc nếu có */
        }

        .intro-s {
            margin-bottom: 50px; /* khoảng cách dưới, nếu dùng */
        }

        .intro-text {
            margin-top: 50px; /* cách biệt phần chữ với ảnh */
        }

        .intro-img {
            width: 120px; /* kích thước ảnh intro */
            height: auto; /* giữ tỉ lệ ảnh */
            border-radius: 12px; /* bo góc cho ảnh */
        }


        .card { /* thẻ chứa chính khi mở card */
            background: rgba(255, 255, 255, 0.95); /* nền hơi mờ trắng */
            border-radius: 30px; /* bo góc lớn */
            padding: 30px; /* khoảng đệm trong */
            width: 100%; /* chiếm width container */
            max-width: 600px; /* giới hạn chiều rộng */
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3); /* bóng đổ */
            z-index: 1; /* đảm bảo hiển thị trên nền */
            animation: slideUp 0.8s ease-out; /* animation xuất hiện */
            backdrop-filter: blur(10px); /* mờ hậu cảnh phía sau card (nếu trình duyệt hỗ trợ) */
        }

        @keyframes slideUp { /* định nghĩa animation slideUp */
            from {
                opacity: 0; /* bắt đầu mờ */
                transform: translateY(50px); /* bắt đầu ở dưới hơn 50px */
            }

            to {
                opacity: 1; /* kết thúc rõ */
                transform: translateY(0); /* về vị trí ban đầu */
            }
        }

        .header h1 {
            font-size: 22px; /* kích thước chữ tiêu đề */
            font-weight: 900; /* chữ đậm */
            text-align: center; /* canh giữa */
            margin-bottom: 25px; /* khoảng cách dưới */
            animation: fadeIn 1s ease-in; /* hiệu ứng mờ vào */
            background: linear-gradient(135deg, #667eea 0%, #eb7272 100%); /* gradient áp cho chữ */
            /* provide the standard property before vendor-prefixed version for broader compatibility */
            background-clip: text; /* chuẩn CSS: lấy phần fill của chữ từ background */
            -webkit-background-clip: text; /* tiền tố WebKit cho Chrome/Safari cũ */
            -webkit-text-fill-color: transparent; /* làm chữ trong suốt để thấy gradient */
        }

        .header h1 .emoji {
            -webkit-text-fill-color: initial; /* đảm bảo emoji có màu mặc định (không bị gradient) */
            font-size: 24px; /* phóng to emoji */
        }

        @keyframes fadeIn {
            from {
                opacity: 0; /* bắt đầu trong suốt */
            }

            to {
                opacity: 1; /* kết thúc rõ */
            }
        }

        .image-container { /* chứa các ảnh slideshow */
            position: relative; /* cần cho các ảnh con position:absolute */
            width: 100%;
            aspect-ratio: 16 / 9; /* giữ tỉ lệ 16:9 */
            border-radius: 20px;
            overflow: hidden; /* ẩn phần tràn */
            margin-bottom: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .slide { /* từng ảnh trong slideshow */
            position: absolute; /* chồng lên nhau */
            inset: 0; /* top/right/bottom/left = 0 */
            width: 100%;
            height: 100%;
            object-fit: cover; /* cắt vừa khung, giữ tỉ lệ */
            left: 100%; /* đặt mặc định ngoài khung ở bên phải */
            opacity: 0; /* ẩn */
            transition: all 1s ease; /* chuyển đổi mượt */
        }

        .slide.active { /* slide đang hiển thị */
            left: 0; /* di chuyển vào khung */
            opacity: 1; /* hiện */
        }

        .slide.prev { /* slide vừa bị chuyển đi */
            left: -100%; /* di chuyển sang trái */
            opacity: 0; /* ẩn */
        }

        .message-box { /* hộp chứa tin nhắn */
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%); /* nền gradient ấm */
            border-radius: 20px;
            padding: 20px;
            width: 100%;
            min-height: 100px; /* đảm bảo có chiều cao */
            display: flex; /* dùng flex để căn giữa nội dung */
            align-items: center; /* căn giữa dọc */
            justify-content: center; /* căn giữa ngang */
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        #message { /* nội dung tin nhắn hiển thị từng ký tự */
            font-size: 18px;
            font-weight: 800;
            color: #4a2c2a; /* màu chữ */
            text-align: center;
            line-height: 1.6; /* khoảng cách dòng */
        }

        .fall { /* lớp cho icon rơi (ví dụ hoa) */
            position: fixed; /* cố định theo viewport */
            top: -50px; /* bắt đầu bên ngoài trên cùng để rơi xuống */
            font-size: 24px; /* kích thước icon */
            animation: fallStraight linear infinite; /* lặp vô hạn */
            opacity: 0.8; /* hơi mờ */
            pointer-events: none; /* không chặn tương tác */
            z-index: 10; /* hiển thị trên phần khác */
        }

        @keyframes fallStraight { /* animation rơi thẳng */
            0% {
                transform: translateY(0); /* vị trí bắt đầu */
                opacity: 1; /* bắt đầu rõ */
            }

            100% {
                transform: translateY(100vh); /* di chuyển xuống hết viewport */
                opacity: 0.3; /* mờ dần khi rơi */
            }
        }

        .footer { /* chân trang cố định */
            position: fixed;
            bottom: 15px; /* cách đáy 15px */
            left: 50%; /* đặt tại giữa ngang */
            transform: translateX(-50%); /* dịch để thật sự canh giữa */
            text-align: center;
            color: #474747;
            font-weight: 600;
            display: flex; /* dùng flex để hỗ trợ icon/label nếu cần */
            align-items: center;
            gap: 5px; /* khoảng cách giữa các phần tử con */
            z-index: 10; /* hiển thị trên các phần khác */
        }

        @media (max-width: 768px) { /* responsive cho màn hình nhỏ hơn 768px */

            html,
            body {
                overflow-x: hidden !important; /* chắc chắn ẩn tràn ngang */
                width: 100%; /* đảm bảo chiếm đủ chiều ngang */
            }

            /* limit element widths on small screens; avoid forcing a top offset on every element */
            *, *::before, *::after {
                max-width: 100%; /* ngăn phần tử vượt quá width của viewport */
            }

            .intro {
                width: 100%;
                padding: 15px;
                text-align: center;
                margin: 0 auto; /* căn giữa block-level */
            }

            .intro-img {
                width: 45%; /* ảnh lớn hơn trên mobile (tỉ lệ phần trăm) */
                max-width: 200px; /* giới hạn tối đa */
                margin: 0 auto;
                display: block; /* đảm bảo có margin auto được áp dụng */
            }

            .intro-text {
                margin-top: 40px;
                font-size: 18px;
                text-align: center;
            }

            .card {
                width: 92%;
                margin: 0 auto;
                padding: 20px;
                border-radius: 25px;
                box-shadow: 0 10px 35px rgba(0, 0, 0, 0.2);
            }

            .header h1 {

            .fall-img {
                position: fixed;
                top: -60px;
                pointer-events: none;
                z-index: 10;
                opacity: 0.95;
                will-change: transform, opacity;
                animation-name: fallStraight;
                animation-timing-function: linear;
                animation-iteration-count: 1;
                transform-origin: center;
                display: block;
            }
                font-size: 20px;
                margin-bottom: 20px;
                text-align: center;
            }

            .image-container {
                width: 100%;
                aspect-ratio: 16 / 9;
                border-radius: 18px;
                margin: 0 auto 20px auto;
                position: relative;
            }

            .slide {
                position: absolute;
                inset: 0;
                width: 100%;
                height: 100%;
                left: 0 !important; /* trên mobile ta đặt luôn tất cả slide ở vị trí để tránh chuyển động lớn */
                object-fit: cover;
            }

            .message-box {
                width: 100%;
                padding: 16px;
                border-radius: 18px;
            }

            #message {
                font-size: 16px;
                line-height: 1.5;
                text-align: center;
            }

            .fall {
                font-size: 18px;
                animation-duration: 3.5s; /* rút ngắn thời gian rơi trên mobile */
            }

            .footer {
                bottom: 10px;
                font-size: 14px;
                left: 50% !important;
                transform: translateX(-50%) !important;
                width: max-content;
                text-align: center;
                margin: 0 auto;
            }
        }

        @media (max-width: 420px) { /* điều chỉnh thêm cho màn rất nhỏ */

            .card {
                padding: 16px;
                width: 94%;
            }

            .intro-img {
                width: 55%;
            }

            #message {
                font-size: 15px;
            }

            .header h1 {
                font-size: 18px;
            }
        }
    </style>
</head>

<body>
    
    <!-- Màn hình chào (intro). Người dùng click vào đây để mở card chính -->
    <div id="intro" class="intro">
        <!-- ví dụ tiêu đề phụ (đang comment) -->
    <img src="D:\Microsoft VS Code\image/manchester-united.png" class="intro-img" />
        <h2 class="intro-text">❤️⚽Ai fan Quỷ Đỏ xin mời nhấn vào⚽❤️</h2> <!-- hướng dẫn click -->
    </div>

    <!-- mainCard: ẩn ban đầu, hiện sau khi người dùng click intro -->
    <div id="mainCard" style="display: none;">
        <div class="card">
            <div class="header">
                <h1>
                    <!-- Sửa lời chúc đầu -->
                    <span class="emoji">🌺</span>
                    Chúc mừng Ngày Nhà giáo Việt Nam 20/11
                    <span class="emoji">🌺</span><br /> <!-- xuống dòng cho tiêu đề -->
                </h1>
            </div>
            <div style="z-index: 9999;" class="image-container"> <!-- slideshow ảnh, z-index cao để hiển thị trên background -->
                <!-- Sửa ảnh chuyển tiếp -->
                <img class="slide active" src="https://drive.google.com/file/d/1s6CLGsIOP1NkZXWK22Csjv7P7jxCrrp9/view?usp=drive_link" alt="Kỷ niệm 1">
                <img class="slide" src="D:\Microsoft VS Code\image/gen-t-anh2.jpg" alt="Kỷ niệm 2">
                <img class="slide" src="D:\Microsoft VS Code\image/gen-n-anh3.jpg" alt="Kỷ niệm 3">
                <img class="slide" src="D:\Microsoft VS Code\image/gen-n-anh4.jpg" alt="Kỷ niệm 4">
                <img class="slide" src="D:\Microsoft VS Code\image/gen-n-anh5.jpg" alt="Kỷ niệm 5">
                <img class="slide" src="D:\Microsoft VS Code\image/gen-h-anh6.jpg" alt="Kỷ niệm 6">
                <img class="slide" src="D:\Microsoft VS Code\image/gen-n-anh7.jpg" alt="Kỷ niệm 7">
            </div>
            <div class="message-box"> <!-- hộp hiển thị tin nhắn/loạn lời chúc -->
                <div id="message"></div> <!-- nơi script sẽ gõ từng ký tự -->
            </div>
        </div>
    </div>
    <script>
        // Lắng nghe sự kiện click vào phần intro để ẩn intro và hiển thị mainCard
        document.getElementById("intro").addEventListener("click", () => {
            document.getElementById("intro").style.display = "none"; // ẩn intro
            document.getElementById("mainCard").style.display = "block"; // hiện nội dung chính

            // Thêm xóa icon rơi xuống ở đây
            const icons = ["🌼", "🌷", "💐", "⚽", "✨", "❤️",];
            setInterval(() => {
                const icon = document.createElement("div"); // tạo 
                icon.classList.add("fall"); 
                icon.innerText = icons[Math.floor(Math.random() * icons.length)]; 
                icon.style.left = Math.random() * 100 + "%";
                icon.style.animationDuration = (Math.random() * 2 + 5) + "s"; 
                document.body.appendChild(icon); 
                setTimeout(() => icon.remove(), 10000); 
            }, 500); 

            typeMessage(); 
        });
        const slides = document.querySelectorAll(".slide");
        let current = 0; 
        function nextSlide() {
            slides[current].classList.remove("active"); 
            slides[current].classList.add("prev"); 
            current = (current + 1) % slides.length; 
            slides[current].classList.add("active"); 
            slides[current].classList.remove("prev");
        }
        setInterval(nextSlide, 4000);
        const messages = [
            "Cảm ơn Thầy đã mang đến cho chúng em tri thức, niềm tin và ước mơ 🌻",
            "Mỗi bài học, mỗi lời dạy của Thầy là hành trang quý giá suốt đời ✨",
            "Kính chúc Thầy luôn mạnh khỏe, hạnh phúc và thành công! 💐",
            "Ngày 20/11 lớp 12A6 xin gửi ngàn lời tri ân đến người Thầy thân yêu ❤️",
            "❤️ Thầy Nguyễn Minh Trí ❤️"
        ]; // mảng các câu chúc sẽ lặp hiển thị
        let msgIndex = 0; // chỉ số cho messages
        let charIndex = 0; // chỉ số ký tự cho hiệu ứng gõ
        const msgContainer = document.getElementById("message"); // nơi hiển thị từng ký tự

        function typeMessage() {
            if (charIndex < messages[msgIndex].length) {
                // nếu chưa gõ hết câu, thêm ký tự tiếp theo
                msgContainer.innerHTML += messages[msgIndex].charAt(charIndex);
                charIndex++;
                setTimeout(typeMessage, 60); // tốc độ gõ 60ms/ký tự
            } else {
                // khi gõ xong câu hiện tại, chờ 3.5s rồi chuyển câu tiếp theo
                setTimeout(() => {
                    msgIndex = (msgIndex + 1) % messages.length; // chuyển câu, quay vòng
                    msgContainer.innerHTML = ""; // xoá nội dung để gõ câu mới
                    charIndex = 0; // reset ký tự
                    typeMessage(); // bắt đầu gõ câu tiếp theo
                }, 3000);
            }
        }
    </script>
</body>

</html>
