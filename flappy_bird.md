#Flappy bird https://docs.google.com/presentation/d/1y7K20vJRz4UjcwAdH02AQcGmS0OtvMA0/edit#slide=id.g23be2d9e8df_0_0
[Flappy Bird](https://studio.code.org/projects/flappy/MFA9GZaYFAOm-R5H8g9aYl7o9A-X9LikRme8BzUunZM)
Flappy Bird là một trò chơi di động cuộn bên có đồ họa 2D theo phong cách cổ điển. Mục tiêu là hướng một con chim đang bay, tên là "Faby", di chuyển liên tục sang phải, giữa các bộ ống giống như Mario. Nếu người chơi chạm vào các đường ống, họ sẽ thua. Faby nhanh chóng bay lên trên mỗi khi người chơi chạm vào màn hình; nếu màn hình không được gõ, Faby sẽ ngã vì trọng lực; mỗi cặp ống mà anh ta điều hướng giữa sẽ kiếm được cho người chơi một điểm. - Từ Wikipedia


##Hướng dẫn các nguyên tắc lập trình cơ bản.
Tổng quan: 
Giúp hs hiểu và khám phá cơ bản của việc phát triển trò chơi và lập trình. Thông qua game Flappy bird và công cụ lập trình trực quan Blockly. 
Flappy bird: dựa vào kịch bản trò chơi để tạo ra chỉ dẫn dạy hs sâu hơn về thuật toán (xử lý sự kiện, xử lý đồ họa, xử lý âm thanh), quy trình (các bước chi tiết) triển khai trò chơi trên các thiết bị, nền tảng công nghệ (phần này tập trung tạo nền tảng và khuyến khích hs tìm tòi khám phá bằng cách cung cấp 1 số từ khóa - tư duy): 
.....
**Phần 1: Sử dụng Blockly để xây dựng trò chơi Flappy Bird**
Key 1: "Blockly". **Cơ bản về Blockly**: Hướng dẫn học sinh về giao diện và cách sử dụng công cụ lập trình trực quan Blockly, cách lập trình hình ảnh với các khối.

Key 2: "Handle events". **Xử lý sự kiện**: Sử dụng khối để bắt sự kiện nhấn phím (ví dụ: mũi tên lên) để làm cho con chim bay lên.

Key 3: "Graphics handling". **Xử lý đồ họa**: Sử dụng khối để vẽ nền và các đối tượng như con chim và ống trên màn hình.

Key 4: "Collision detection". **Xử lý va chạm**: Giới thiệu cách sử dụng khối để kiểm tra va chạm giữa con chim và ống, và hiển thị kết quả thua cuộc hoặc tiếp tục chơi.

Key 5: "Sound integration". **Xử lý âm thanh**: Sử dụng khối để thêm âm thanh khi con chim bay và khi va chạm xảy ra.

**Phần 2: Khám phá và tìm tòi**
1. **Hiệu chỉnh trò chơi**: Khuyến khích học sinh thử nghiệm bằng cách thay đổi độ khó của trò chơi, thay đổi màu sắc và hình dạng của các đối tượng.

2. **Tạo thêm tính năng**: Hướng dẫn học sinh tìm hiểu và thêm tính năng như lưu điểm số, tạo màn chơi mới hoặc thay đổi cách con chim di chuyển. thậm chí nâng cao trải nghiệm -  kết nối mạng để thi đấu trực tuyến.

3. **Học thêm về lập trình**: Khuyến khích học sinh nghiên cứu các khái niệm lập trình nâng cao như biến, vòng lặp và điều kiện.

4. **Khám phá nền tảng khác**: Đề cập đến việc phát triển trò chơi bằng các ngôn ngữ lập trình như Python hoặc sử dụng các công cụ phát triển trò chơi như Unity (C#) hoặc Godot (GDScript)

**Phần 3: Triển khai trò chơi**
1. **Chạy trò chơi trên máy tính**: Hướng dẫn học sinh cách chạy trò chơi Flappy Bird thông qua Blockly trên máy tính để kiểm tra kết quả.

2. **Khám phá triển khai trên nền tảng khác**: Khuyến khích học sinh tìm hiểu về cách triển khai trò chơi trên các thiết bị di động hoặc trình duyệt web.

3. **Tìm hiểu thêm về thuật toán**: Khuyến khích học sinh nghiên cứu các thuật toán xử lý va chạm, kiểm tra đụng độ và quản lý vị trí đối tượng trong trò chơi.
.....

###Hướng dẫn triển khai trò chơi.
Trong dự án này, chúng ta thiết kế và triển khai trò chơi Flappy Bird trên nền tảng trực tuyến.
Tổng quan:
Trò chơi này, người chơi có khả năng thao tác chuyển động thẳng đứng của một con chim. Bằng cách nhấn phím, người chơi có thể khiến con chim nhảy lên một khoảng nhất định, sau đó con chim sẽ rơi tự do mất kiểm soát nếu không tiếp tục nhấn phím.

Kịch bản: 
Ngay khi trò chơi bắt đầu, các ống (chướng ngại vật) sẽ không ngừng xuất hiện từ phía bên phải màn hình và di chuyển sang phía trái (Mục đích của việc này là để tạo cảm giác như con chim đang bay tiến về phía trước).
Người chơi phải tận dụng khả năng điều khiển con chim để né tránh và vượt qua các ống.(đòi hỏi người chơi phải có ước tính thời gian và khoảng cách chính xác để tránh va chạm với các ống). Điểm số của người chơi sẽ tăng lên mỗi khi con chim vượt qua một ống.
Trò chơi sẽ tiếp tục diễn ra mà không giới hạn thời gian cho đến khi con chim va vào một trong các ống hoặc chạm vào mặt đất. Khi điều này xảy ra, trò chơi sẽ kết thúc và người chơi có thể xem điểm số của mình để thách thức bản thân và cải thiện thành tích trong lần chơi tiếp theo.

Hình 1 là màn hình bắt đầu của Flappy Bird. Tiêu đề "Flappy Bird" được hiển thị ở giữa
phía trên của màn hình. Con chim cũng được hiển thị trên nền.
Hình 2 là màn hình khi người chơi đã nhấn bắt đầu, kịch bản trò chơi bắt đầu diễn ra.
Hình 3 là màn hình diễn ra xử lý sự kiện, va chạm, âm thanh.
Hình 4 là màn hình khi kịch bản trò chơi kết thúc: thông tin điểm số, phần thưởng, tên được hiển thị ở giữa màn hình.

Chi tiết triển khai trò chơi:
Thực hiện logic trò chơi bằng ngôn ngữ lập trình trực quan Blockly (kéo thả). Các khối lệnh được kéo thả vào workspace sẽ thực thi các chức năng logic trò chơi. 
Thực hành theo mô-đun chức năng:
1. **When run (Khi bắt đầu):**
   Mô-đun này có nhiệm vụ thiết lập trạng thái ban đầu của trò chơi và sẽ được thực hiện khi người chơi nhấn nút "Run" để bắt đầu trò chơi. Các khối lệnh trong mô-đun này sẽ xác định các yếu tố như vị trí ban đầu của con chim và các giá trị khởi đầu khác: kéo thả các lệnh tương ứng vào workspace và đặt phía dưới When run.

2. **When click (Khi nhấp chuột):**
   Mô-đun này sẽ điều khiển sprite (nhân vật trong trò chơi) và sẽ được kích hoạt khi người chơi nhấp chuột. Các khối lệnh trong mô-đun này sẽ quản lý hành vi của sprite khi người chơi thực hiện thao tác nhấp chuột, chẳng hạn như di chuyển sprite lên trên khi người chơi nhấp: kéo thả các lệnh tương ứng vào workspace và đặt phía dưới When click.

3. **When hit the ground (Khi va chạm với mặt đất) và When hit an obstacle (Khi va chạm với vật cản):**
   Những mô-đun này sẽ xử lý tình huống khi con chim va chạm với mặt đất hoặc vật cản. Các khối lệnh trong mô-đun này sẽ xác định hành động sau va chạm, chẳng hạn như kết thúc trò chơi hoặc tính toán điểm số dựa trên số cột đã vượt qua.(When pass obstacle): kéo thả các lệnh tương ứng vào workspace và đặt phía dưới When hit the ground và When hit an obstacle.

4. **When pass obstacle (Khi vượt qua vật cản):**
   Mô-đun này sẽ thực hiện khi con chim vượt qua một vật cản. Các khối lệnh trong mô-đun này sẽ quản lý việc tính điểm, cung cấp phần thưởng và điều chỉnh kịch bản trò chơi dựa trên việc vượt qua vật cản: kéo thả các lệnh tương ứng vào workspace và đặt phía dưới When pass obstacle.


**Các mô-đun con cho bộ điều khiển logic trò chơi:**

Dựa trên các chức năng đã được đặc tả, cần có ba mô-đun con riêng biệt cho bộ điều khiển logic trò chơi. Những mô-đun này sẽ tương tác với nhau và thực hiện các nhiệm vụ cụ thể trong trò chơi:
1. Trình điều khiển - Chuột (Click): sử dụng chuột (mặc định) trái.
2. Bộ điều khiển hành động:
Flap a 'value' amount:
- Hành động "flap" (vỗ cánh) sẽ được thực hiện với một giá trị cụ thể. Điều này có thể ảnh hưởng đến chuyển động của nhân vật.
3. Bộ điều khiển âm thanh:
Play 'value' sound
- Âm thanh trong trò chơi sẽ được điều khiển thông qua việc phát phát lại âm thanh có giá trị cụ thể. Điều này giúp tạo ra hiệu ứng âm thanh phù hợp với các sự kiện trong trò chơi.
4. Bộ điều khiển Sprite: 
Set speed 'value', 
set scene 'value', 
set player 'value', 
set obstacle 'value', 
set ground, set a 'value'
grap, set gravity 'value', 
set score 'value'.
- Bộ điều khiển Sprite sẽ điều chỉnh các tham số quan trọng trong trò chơi: tốc độ, cảnh, người chơi, vật cản, mặt đất, lực kéo, điểm số và các giá trị khác.

###Sản phẩm cuối cùng:
Hs tạo ra 1 trò chơi tương tự Flappy bird của riêng mình, có tính cá nhân hóa riêng: nhân vật, giao diện, kịch bản trò chơi. Trò chơi được đóng gói miễn phí cho phép hs chia sẻ trò chơi trên các nền tảng xã hội hoặc sử dụng phi lợi nhuận.

###Bài học kinh nghiệm và vấn đề.
Đây là phiên bản học tập nên chúng ta tập trung nhiều hơn vào hiểu các vấn đề của trò chơi như nhân vật, kịch bản, thiết lập,..
Phiên bản học tập trên web còn hạn chế 1 số thiết lập cần thiết nữa cho 1 trò chơi hoàn chỉnh.

Lời khuyên và phát triển trong tương lai. 
Mã hóa có thể là khó hiểu nhưng chúng chính là những gì máy hiểu. Nó sẽ giúp chúng ta làm việc với máy tính chuyên sâu hơn.
Có nhiều ngôn ngữ lập trình hay các cách phát triển game bằng những công cụ khác nhau, hãy thực hành nó trên những ngôn ngữ lập trình hoặc công cụ phát triển trò chơi mà bạn hiểu rõ.
Chọn ảnh sprite có độ phân giải cao và loại bỏ nền sprite rõ ràng hơn, có thể làm cho hình ảnh trò chơi của chúng tôi trông đẹp hơn.
Thiết kế logic trò chơi phức tạp hơn có thể tăng tính toàn vẹn trò chơi. Từ ví dụ, nền thay đổi theo thời gian, khoảng cách giữa các cột trở nên ngẫu nhiên.

###FAQ:
**Vì sao sử dụng Blockly?**
Blockly là một công cụ lập trình trực quan giúp bạn tạo mã bằng cách kéo và thả các khối lệnh. Điều này giúp loại bỏ gánh nặng của việc phải nhớ cú pháp lập trình và tập trung vào ý tưởng và logic. Chúng tôi chọn sử dụng Blockly vì nó là cách tuyệt vời để giúp người học mới tiếp cận lập trình một cách dễ dàng và thú vị mà không cần đầu tư quá nhiều thời gian vào việc học cú pháp mã lệnh.
**Vì sao sử dụng Flappy bird?**
Chúng tôi chọn sử dụng trò chơi Flappy Bird để hướng dẫn về lập trình vì nó là một trò chơi đơn giản nhưng vô cùng thú vị. Flappy Bird đòi hỏi người chơi phải sử dụng các nguyên tắc cơ bản của lập trình như xử lý sự kiện, xử lý đồ họa, và quản lý trạng thái để có thể điều khiển con chim bay qua các ống.
Thông qua việc phát triển trò chơi Flappy Bird, học sinh có thể:
- Hiểu cách áp dụng kiến thức lập trình vào việc tạo ra một trò chơi hoàn chỉnh.
- Nắm vững các khái niệm cơ bản như xử lý sự kiện, vẽ đồ họa, xử lý va chạm và tích hợp âm thanh.
- Thực hành các kỹ năng lập trình một cách thực tế và thú vị.
- Học cách giải quyết vấn đề và logic thông qua việc thiết kế các chức năng trong trò chơi.
**Vì sao?**

**Hành trình của bạn trong khóa học:**



