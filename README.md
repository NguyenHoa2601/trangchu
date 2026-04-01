AI đang dùng: Gemini.

Lệnh: 
<pre><code>
&lt;!DOCTYPE html&gt;
&lt;html lang="vi"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;title&gt;Giao diện Apple&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;

    &lt;div id="vung1"&gt;
        &lt;span&gt;Chọn quốc gia hoặc khu vực khác để xem nội dung dành riêng cho vị trí của bạn...&lt;/span&gt;
        &lt;span&gt;&lt;b&gt;Việt Nam&lt;/b&gt;&lt;/span&gt;
        &lt;button&gt;Tiếp tục&lt;/button&gt;
    &lt;/div&gt;

    &lt;div id="vung2"&gt;
        &lt;a&gt;Store&lt;/a&gt;
        &lt;a&gt;Mac&lt;/a&gt;
        &lt;a&gt;iPad&lt;/a&gt;
        &lt;a&gt;iPhone&lt;/a&gt;
        &lt;a&gt;Watch&lt;/a&gt;
        &lt;a&gt;Vision&lt;/a&gt;
        &lt;a&gt;AirPods&lt;/a&gt;
        &lt;a&gt;TV &amp; Home&lt;/a&gt;
        &lt;a&gt;Entertainment&lt;/a&gt;
        &lt;a&gt;Accessories&lt;/a&gt;
        &lt;a&gt;Support&lt;/a&gt;
    &lt;/div&gt;

    &lt;div id="vung3"&gt;
    &lt;center&gt;
        &lt;h1&gt;MacBook Neo&lt;/h1&gt;
        &lt;p&gt;Amazing Mac. Surprising price.&lt;/p&gt;
    &lt;/center&gt;
    &lt;/div&gt;

    &lt;div id="vung4"&gt;
    &lt;center&gt;
        &lt;a&gt;Learn more&lt;/a&gt;
        &lt;a&gt;Buy&lt;/a&gt;
    &lt;/center&gt;
    &lt;/div&gt;

    &lt;div id="vung5"&gt;
        &lt;center&gt;
        &lt;img src="https://cdn2.cellphones.com.vn/insecure/rs:fill:0:0/q:100/plain/https://cellphones.com.vn/media/wysiwyg/laptop/macbook/Neo/macbook-neo-8.jpg" alt="MacBook Neo" width="600"&gt;
        &lt;/center&gt;
    &lt;/div&gt;

&lt;/body&gt;
&lt;/html&gt;
</code></pre>

Hãy viết CSS cho đoạn mã HTML có sẵn của tôi (giữ nguyên cấu trúc HTML). Yêu cầu phong cách Apple Design System:
Tổng thể: Sử dụng font sans-serif (như SF Pro hoặc Inter), màu chữ đen nhám (#1d1d1f), nền trắng tinh khôi.
Navigation (#vung2): Dàn hàng ngang, dùng flexbox, chữ nhỏ thanh mảnh, có hiệu ứng hover mờ nhẹ và thanh menu cố định (sticky) khi cuộn.
Typography (#vung3): Tiêu đề h1 thật lớn, đậm; đoạn văn p phía dưới nhẹ nhàng, tinh tế.
Nút bấm (#vung4): Biến 2 thẻ <a> thành nút bấm bo tròn (pill-shaped). Một nút dạng Outline (chỉ có viền xanh) và một nút dạng Solid (nền xanh chữ trắng). Thêm hiệu ứng transition mượt mà.
Hình ảnh: Căn giữa và giới hạn chiều rộng tối đa để không bị tràn màn hình.

Kết quả:

Trước:
<img width="1874" height="962" alt="image" src="https://github.com/user-attachments/assets/db51c0a5-5445-4e35-a28b-49a6a73b61ea" />


Sau:
<img width="1863" height="964" alt="image" src="https://github.com/user-attachments/assets/6ff2e198-09ec-4790-ac8f-575267662ed2" />

Mã sau khi ra lệnh:
<pre><code>
&lt;!DOCTYPE html&gt;
&lt;html lang="vi"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
    &lt;title&gt;Giao diện Apple - MacBook Neo&lt;/title&gt;
    &lt;style&gt;
        /* 1. Reset &amp; Typography */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "SF Pro Icons", "Helvetica Neue", Helvetica, Arial, sans-serif;
            background-color: #ffffff;
            color: #1d1d1f;
            line-height: 1.47059;
            font-weight: 400;
            letter-spacing: -0.022em;
            -webkit-font-smoothing: antialiased;
        }

        /* 2. Vùng 1: Banner thông báo */
        #vung1 {
            background-color: #f5f5f7;
            padding: 12px 20px;
            text-align: center;
            font-size: 12px;
            color: #1d1d1f;
        }

        #vung1 b {
            font-weight: 600;
            margin-left: 4px;
        }

        #vung1 button {
            background: none;
            border: none;
            color: #0066cc;
            cursor: pointer;
            margin-left: 10px;
            font-size: 12px;
            padding: 0;
        }

        #vung1 button:hover {
            text-decoration: underline;
        }

        /* 3. Vùng 2: Navigation - Sticky &amp; Glassmorphism */
        #vung2 {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 32px;
            height: 44px;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: saturate(180%) blur(20px);
            position: sticky;
            top: 0;
            z-index: 9999;
            border-bottom: 1px solid rgba(0,0,0,0.1);
        }

        #vung2 a {
            text-decoration: none;
            color: #1d1d1f;
            font-size: 12px;
            opacity: 0.8;
            transition: opacity 0.3s cubic-bezier(0.25, 0.1, 0.25, 1);
            cursor: pointer;
            font-weight: 400;
        }

        #vung2 a:hover {
            opacity: 1;
            color: #0066cc;
        }

        /* 4. Vùng 3: Headline Typography */
        #vung3 {
            padding-top: 80px;
            text-align: center;
        }

        #vung3 h1 {
            font-size: 56px;
            line-height: 1.07143;
            font-weight: 600;
            letter-spacing: -0.005em;
            margin-bottom: 6px;
        }

        #vung3 p {
            font-size: 24px;
            line-height: 1.16667;
            font-weight: 400;
            letter-spacing: .009em;
            color: #1d1d1f;
        }

        /* 5. Vùng 4: Buttons (Pill-shaped) */
        #vung4 {
            margin-top: 15px;
            margin-bottom: 50px;
            text-align: center;
        }

        #vung4 a {
            display: inline-block;
            padding: 8px 16px;
            font-size: 17px;
            line-height: 1.17648;
            font-weight: 400;
            letter-spacing: -0.022em;
            border-radius: 980px;
            text-decoration: none;
            margin: 0 10px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        /* Nút Learn more (Dạng Solid Blue) */
        #vung4 a:first-child {
            background-color: #0066cc;
            color: #fff;
            border: 1px solid #0066cc;
        }

        #vung4 a:first-child:hover {
            background-color: #0071e3;
            border-color: #0071e3;
        }

        /* Nút Buy (Dạng Outline Blue) */
        #vung4 a:last-child {
            background-color: transparent;
            color: #0066cc;
            border: 1px solid #0066cc;
        }

        #vung4 a:last-child:hover {
            background-color: #0066cc;
            color: #fff;
        }

        /* 6. Vùng 5: Image centering &amp; Responsive */
        #vung5 {
            text-align: center;
            padding-bottom: 100px;
            max-width: 1000px;
            margin: 0 auto;
        }

        #vung5 img {
            max-width: 90%;
            height: auto;
            display: block;
            margin: 0 auto;
            border-radius: 12px;
        }

        /* Responsive cho Mobile */
        @media (max-width: 734px) {
            #vung3 h1 { font-size: 40px; }
            #vung3 p { font-size: 19px; }
            #vung2 { 
                gap: 15px; 
                overflow-x: auto; 
                justify-content: flex-start; 
                padding: 0 20px; 
            }
        }
    &lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;

    &lt;div id="vung1"&gt;
        &lt;span&gt;Chọn quốc gia hoặc khu vực khác để xem nội dung dành riêng cho vị trí của bạn...&lt;/span&gt;
        &lt;span&gt;&lt;b&gt;Việt Nam&lt;/b&gt;&lt;/span&gt;
        &lt;button&gt;Tiếp tục&lt;/button&gt;
    &lt;/div&gt;

    &lt;div id="vung2"&gt;
        &lt;a&gt;Store&lt;/a&gt;
        &lt;a&gt;Mac&lt;/a&gt;
        &lt;a&gt;iPad&lt;/a&gt;
        &lt;a&gt;iPhone&lt;/a&gt;
        &lt;a&gt;Watch&lt;/a&gt;
        &lt;a&gt;Vision&lt;/a&gt;
        &lt;a&gt;AirPods&lt;/a&gt;
        &lt;a&gt;TV &amp; Home&lt;/a&gt;
        &lt;a&gt;Entertainment&lt;/a&gt;
        &lt;a&gt;Accessories&lt;/a&gt;
        &lt;a&gt;Support&lt;/a&gt;
    &lt;/div&gt;

    &lt;header id="vung3"&gt;
        &lt;h1&gt;MacBook Neo&lt;/h1&gt;
        &lt;p&gt;Amazing Mac. Surprising price.&lt;/p&gt;
    &lt;/header&gt;

    &lt;div id="vung4"&gt;
        &lt;a&gt;Learn more&lt;/a&gt;
        &lt;a&gt;Buy&lt;/a&gt;
    &lt;/div&gt;

    &lt;div id="vung5"&gt;
        &lt;img src="https://cdn2.cellphones.com.vn/insecure/rs:fill:0:0/q:100/plain/https://cellphones.com.vn/media/wysiwyg/laptop/macbook/Neo/macbook-neo-8.jpg" alt="MacBook Neo"&gt;
    &lt;/div&gt;

&lt;/body&gt;
&lt;/html&gt;
</code></pre>

