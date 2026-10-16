
# 🚀 Smart-Farm IoT – Hệ thống tưới tiêu thông minh tại Trang trại Lan

## 1. Giới thiệu dự án

Smart-Farm IoT là hệ thống giám sát môi trường và tự động hóa tưới tiêu, được phát triển nhằm giúp Trang trại Lan sử dụng nước hiệu quả, giảm công sức vận hành và nâng cao chất lượng chăm sóc cây trồng.

Hệ thống thu thập dữ liệu từ cảm biến, xử lý thông tin bằng bộ điều khiển IoT và kích hoạt máy bơm hoặc van tưới khi đáp ứng các điều kiện đã cấu hình.

**Mục tiêu chính:** Tự động hóa quá trình tưới cây dựa trên dữ liệu môi trường, đồng thời hỗ trợ người vận hành theo dõi trạng thái hệ thống.

## 2. Phân tích hệ thống theo mô hình IPO

Mô hình IPO gồm Input, Process và Output, giúp xác định dữ liệu đầu vào, quá trình xử lý và kết quả đầu ra của hệ thống.

Thành phần

Mô tả

Ví dụ

Input

Thu thập dữ liệu từ môi trường

Nhiệt độ, độ ẩm không khí, độ ẩm đất

Process

Phân tích dữ liệu và ra quyết định

So sánh với ngưỡng cấu hình

Output

Thực hiện hành động hoặc thông báo

Bật máy bơm, mở van tưới, gửi cảnh báo

### 2.1. Sơ đồ phối hợp phần cứng

  

_Alt Text:_ Sơ đồ hệ thống Smart-Farm IoT thể hiện luồng dữ liệu từ cảm biến đến bộ điều khiển và luồng điều khiển từ bộ điều khiển đến máy bơm hoặc van tưới.

Luồng hoạt động cơ bản:

1.  Cảm biến đo nhiệt độ và độ ẩm của môi trường.
    
2.  Bộ điều khiển IoT đọc dữ liệu và kiểm tra tính hợp lệ.
    
3.  Chương trình xử lý so sánh dữ liệu với các ngưỡng đã cấu hình.
    
4.  Bộ điều khiển gửi tín hiệu đến mạch điều khiển máy bơm hoặc van tưới.
    
5.  Hệ thống ghi nhận trạng thái và thông báo cho người vận hành nếu cần.
    

Lưu ý: Tên và số lượng cảm biến, bộ điều khiển cũng như thiết bị chấp hành cần được cập nhật theo phần cứng thực tế của dự án.

## 3. Kiến trúc phần cứng và SoC

### 3.1. Các thành phần chính

Thành phần

Chức năng

Cảm biến

Đo nhiệt độ, độ ẩm không khí hoặc độ ẩm đất

Bộ điều khiển IoT

Thu thập dữ liệu, xử lý logic và điều khiển thiết bị

CPU

Thực thi các lệnh của chương trình điều khiển

RAM

Lưu tạm dữ liệu, biến chương trình và nhật ký đang xử lý

Bộ nhớ lưu trữ

Lưu chương trình, cấu hình và nhật ký cần giữ lâu dài

Mạch điều khiển

Cách ly hoặc khuếch đại tín hiệu điều khiển thiết bị công suất

Máy bơm hoặc van tưới

Cấp nước cho khu vực trồng cây

Kết nối mạng

Truyền dữ liệu giám sát khi được trang bị

### 3.2. System on a Chip (SoC)

SoC là hệ thống tích hợp nhiều thành phần điện tử trên cùng một chip, có thể bao gồm CPU, bộ điều khiển bộ nhớ, giao tiếp ngoại vi và các khối chức năng khác.

Trong dự án Smart-Farm, nếu sử dụng bộ điều khiển dựa trên SoC, chip có thể đảm nhiệm việc đọc dữ liệu cảm biến, xử lý chương trình và giao tiếp với các thiết bị ngoại vi.

Cần phân biệt: SoC là một hệ thống tích hợp trên chip, còn CPU là thành phần thực thi các lệnh chương trình. Không phải mọi bộ điều khiển IoT đều có cấu trúc SoC giống nhau.

### 3.3. Chu trình Fetch–Decode–Execute

Khi bộ điều khiển nhận được yêu cầu bật hệ thống tưới, CPU thực hiện các lệnh chương trình theo chu trình cơ bản dưới đây.

> **Fetch – Nạp lệnh:** CPU lấy lệnh tiếp theo từ bộ nhớ chương trình.
> 
> **Decode – Giải mã:** CPU xác định ý nghĩa của lệnh, chẳng hạn đọc giá trị cảm biến hoặc kiểm tra điều kiện tưới.
> 
> **Execute – Thực thi:** CPU thực hiện phép tính hoặc thao tác tương ứng, ví dụ xác định độ ẩm đất thấp hơn ngưỡng cho phép và yêu cầu bật máy bơm.
> 
> **Kết quả:** Bộ điều khiển gửi tín hiệu đến mạch điều khiển thiết bị. CPU không trực tiếp cấp điện cho máy bơm công suất lớn.

Chu trình này lặp lại trong quá trình chương trình vận hành. Việc bật máy bơm thực tế còn phụ thuộc vào logic điều khiển, trạng thái thiết bị và các cơ chế an toàn.

## 4. Tháp DIKW – Chuyển đổi dữ liệu thành quyết định tưới

DIKW là mô hình thể hiện quá trình chuyển đổi từ Data (Dữ liệu), Information (Thông tin), Knowledge (Tri thức) đến Wisdom (Sự khôn ngoan hoặc khả năng ra quyết định).

```
                 /\
                /  \
               / W  \       WISDOM
              /------\      Quyết định tưới
             /   K    \     KNOWLEDGE
            /----------\    Tri thức về điều kiện tưới
           /     I      \   INFORMATION
          /--------------\  Thông tin đã xử lý
         /       D        \ DATA
        /__________________\ Dữ liệu cảm biến
```

### Ví dụ áp dụng tại Trang trại Lan

Cấp độ

Ví dụ

Data – Dữ liệu

Cảm biến độ ẩm đất trả về 24%

Information – Thông tin

Độ ẩm đất hiện thấp hơn ngưỡng cấu hình 30%

Knowledge – Tri thức

Cây trồng tại khu vực này cần được tưới khi độ ẩm đất xuống dưới ngưỡng đã xác định

Wisdom – Quyết định

Kiểm tra điều kiện an toàn rồi bật tưới trong khoảng thời gian phù hợp; tiếp tục theo dõi và dừng khi đạt điều kiện kết thúc

Các giá trị 24% và 30% chỉ là ví dụ minh họa, không phải thông số khuyến nghị cho mọi loại cây. Ngưỡng tưới thực tế cần được xác định theo loại cây, loại đất và phương pháp đo.

## 5. Tính năng chính

-   Thu thập dữ liệu từ cảm biến được hỗ trợ.
    
-   Xử lý dữ liệu theo ngưỡng cấu hình.
    
-   Điều khiển máy bơm hoặc van tưới thông qua mạch điều khiển phù hợp.
    
-   Ghi nhận trạng thái hoạt động và các sự kiện quan trọng.
    
-   Xây dựng giao diện giám sát từ xa.
    
-   Gửi cảnh báo khi phát hiện lỗi cảm biến hoặc thiết bị.
    
-   Tối ưu lịch tưới theo dữ liệu lịch sử và nhu cầu của cây trồng.
    

Các mục chưa hoàn thành cần được cập nhật sau khi chức năng được triển khai và kiểm thử thành công.

## 6. Yêu cầu hệ thống

Hạng mục

Yêu cầu

Bộ điều khiển

Bo mạch IoT tương thích với cảm biến và thiết bị ngoại vi

Cảm biến

Tương thích với giao tiếp của bộ điều khiển

Thiết bị tưới

Máy bơm hoặc van có thông số điện phù hợp

Nguồn điện

Đáp ứng yêu cầu của bộ điều khiển và thiết bị chấp hành

Mạng

Wi-Fi hoặc phương thức kết nối khác nếu cần giám sát từ xa

Phần mềm

Firmware điều khiển và công cụ nạp chương trình tương ứng

Lưu trữ

Có phương án quản lý nhật ký và dữ liệu cần lưu lâu dài

Thông số điện áp, dòng điện, dung lượng RAM và loại cảm biến phải được bổ sung từ tài liệu phần cứng thực tế trước khi triển khai.

## 7. Cài đặt và triển khai

### 7.1. Chuẩn bị

-   Bộ điều khiển IoT tương thích.
    
-   Cảm biến và thiết bị tưới.
    
-   Máy tính có công cụ lập trình phù hợp.
    
-   Mã nguồn firmware và tài liệu đấu nối.
    
-   Nguồn điện đúng thông số kỹ thuật.
    

### 7.2. Các bước cài đặt

Hiện chưa có thông tin về bo mạch và framework cụ thể, vì vậy các lệnh dưới đây là ví dụ minh họa cho quy trình quản lý mã nguồn. Hãy thay bằng lệnh phù hợp với dự án thực tế.

```
# 1. Tải mã nguồn dự án
git clone <URL_REPOSITORY>

# 2. Đi vào thư mục dự án
cd <PROJECT_DIRECTORY>

# 3. Đọc hướng dẫn cài đặt của firmware
# Thực hiện cài đặt thư viện theo nền tảng đang sử dụng

# 4. Cấu hình cảm biến, ngưỡng tưới và kết nối
# Cập nhật tệp cấu hình theo môi trường triển khai

# 5. Biên dịch và nạp firmware
# Sử dụng công cụ tương ứng với bo mạch
```

Không chạy nguyên các lệnh có phần giữ chỗ trong dấu ngoặc nhọn. Cần thay chúng bằng địa chỉ kho mã nguồn và tên thư mục thật.

### 7.3. Cấu hình trước khi vận hành

1.  Khai báo loại cảm biến và chân kết nối.
    
2.  Cấu hình ngưỡng tưới phù hợp với cây trồng.
    
3.  Kiểm tra chiều hoạt động của relay, van và máy bơm.
    
4.  Thiết lập thời gian tưới tối đa và điều kiện dừng an toàn.
    
5.  Kiểm tra xử lý lỗi khi cảm biến mất kết nối.
    
6.  Chạy thử ở chế độ không tải hoặc mô phỏng trước khi cấp nước thực tế.
    

## 8. Kiểm thử và xử lý sự cố

Tình huống

Cách kiểm tra

Hướng xử lý

Cảm biến không trả dữ liệu

Kiểm tra dây nối, nguồn và giao tiếp

Đánh dấu dữ liệu không hợp lệ và không quyết định tưới dựa trên dữ liệu lỗi

Độ ẩm thấp nhưng bơm không chạy

Kiểm tra ngưỡng, trạng thái relay và nguồn cấp

Kiểm tra lần lượt chương trình và mạch điều khiển

Bơm không dừng

Kiểm tra điều kiện kết thúc và bộ định thời

Ngắt theo cơ chế an toàn và kiểm tra thiết bị

Mất kết nối mạng

Kiểm tra trạng thái kết nối

Duy trì chế độ cục bộ an toàn nếu thiết kế hỗ trợ

RAM gần đầy

Kiểm tra mức sử dụng bộ nhớ và kích thước nhật ký

Giới hạn log, giải phóng bộ đệm và chuyển dữ liệu cần giữ sang lưu trữ phù hợp

## 9. Lưu ý an toàn khi RAM đầy

RAM là bộ nhớ tạm thời dùng để lưu dữ liệu và trạng thái phục vụ chương trình đang chạy. Nếu nhật ký được lưu liên tục mà không có giới hạn, RAM có thể cạn kiệt, dẫn đến giảm hiệu năng, lỗi cấp phát bộ nhớ hoặc khởi động lại bộ điều khiển.

Các biện pháp đề xuất:

-   Giới hạn kích thước bộ đệm nhật ký và số lượng bản ghi giữ trong RAM.
    
-   Chỉ ghi các sự kiện cần thiết; tránh tạo log quá thường xuyên trong vòng lặp điều khiển.
    
-   Chuyển nhật ký cần lưu lâu dài sang bộ nhớ phù hợp, chẳng hạn bộ nhớ flash hoặc máy chủ nếu hệ thống hỗ trợ.
    
-   Theo dõi mức sử dụng RAM và phát cảnh báo trước khi bộ nhớ cạn.
    
-   Giải phóng tài nguyên không còn sử dụng và kiểm tra nguy cơ rò rỉ bộ nhớ.
    
-   Không xóa dữ liệu quan trọng một cách tùy tiện chỉ để giải phóng RAM.
    
-   Không tự động khởi động lại bộ điều khiển khi chưa đánh giá ảnh hưởng đến quá trình tưới.
    
-   Thiết kế trạng thái an toàn cho máy bơm và van khi chương trình gặp lỗi, mất cảm biến hoặc khởi động lại.
    

**Nguyên tắc an toàn:** Khi xảy ra lỗi bộ nhớ, hệ thống phải xử lý theo chính sách an toàn đã được thiết kế và kiểm thử. Trạng thái bật hoặc tắt máy bơm cần được xác định dựa trên rủi ro thực tế, không nên mặc định một trạng thái duy nhất phù hợp cho mọi hệ thống.

## 10. Bảo trì và vận hành

-   Kiểm tra cảm biến định kỳ và hiệu chuẩn khi cần thiết.
    
-   Kiểm tra đường ống, van và máy bơm.
    
-   Theo dõi nhật ký lỗi và mức sử dụng bộ nhớ.
    
-   Sao lưu cấu hình trước khi cập nhật firmware.
    
-   Kiểm thử lại các cơ chế dừng khẩn cấp sau mỗi lần thay đổi phần cứng hoặc phần mềm.
    
-   Ghi lại phiên bản firmware, ngày bảo trì và các thay đổi cấu hình.
    

## 11. Giới hạn và hướng phát triển

Phiên bản hiện tại tập trung vào giám sát dữ liệu và điều khiển tưới theo ngưỡng. Các hướng phát triển có thể bao gồm:

-   Xây dựng bảng điều khiển giám sát từ xa.
    
-   Lưu trữ và trực quan hóa dữ liệu lịch sử.
    
-   Tích hợp dự báo thời tiết để hỗ trợ lập lịch tưới.
    
-   Phân tích nhu cầu nước theo loại cây và từng khu vực.
    
-   Bổ sung cơ chế xác thực, bảo vệ cấu hình và cập nhật firmware an toàn.
    

## 12. Thông tin dự án

Trường thông tin

Giá trị

Tên dự án

Smart-Farm IoT

Đơn vị triển khai

Trang trại Lan

Loại dự án

Nông nghiệp thông minh và IoT

Tài liệu

README.md

Phiên bản tài liệu

1.0

Trạng thái

Mẫu tài liệu, cần xác minh theo hệ thống thực tế

----------

_Tài liệu này là mẫu bàn giao kỹ thuật. Trước khi sử dụng chính thức, cần cập nhật thông số phần cứng, sơ đồ đấu nối, lệnh cài đặt, ngưỡng tưới và kết quả kiểm thử theo sản phẩm thực tế._
