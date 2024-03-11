# SaleSync API Definition Repository
## Giới thiệu

Repository này được tạo ra nhằm làm cầu nối giao tiếp giữa front-end và back-end trong việc định nghĩa request, response cần thiết.

## Cách viết một định nghĩa API
### Xác định service cần gọi

- Dựa vào Schema và luồng các màn hình, người thiết kế cần xác định rõ sẽ gọi request trên service nào đầu tiên.
- Viết request trong file tương ứng với service. (Tạo mới nếu file chưa tồn tại)

*Ví dụ*: Gọi API để hiển thị toàn bộ Lead $\rightarrow$ Xác định gọi `record-service` $\rightarrow$ Viết API trong file `record-service`.
### Định nghĩa endpoint
- Định nghĩa endpoint và đặt tên cho đường dẫn.
- Định nghĩa phương thức request (`GET`, `POST`, `PUT`,...)

*Ví dụ*: Trong file `record-service`, bắt đầu dòng mới bằng hình thức:

    // Other definition...

    GET [API_ENTRY]/record/lead/get-all

Sau đó viết tiếp API definition bằng cách **thụt hàng vào trong 2 tab size**.

### Định nghĩa Parameter, Header, Body cần thiết (nếu có)

- Có thể bỏ qua những parameter **KHÔNG** phục vụ mục đích chính của request.
- Bắt đầu bằng từ khoá `PARAM:`, `HEADER`, `BODY:` và viết định nghĩa bằng hình thức JSON.

      // Other definition...
      POST [API_ENTRY]/record/lead/create
          PARAM: {
            someKey: 'value',
            anotherKey:  'value',
          }
          HEADER: {
            someKey: 'value',
            anotherKey:  'value',
          }
          BODY: {
            someKey: 'value',
            anotherKey:  'value',
          }

### Định  nghĩa response cần có

- Đây là bước cuối, định nghĩa được response mà client-side muốn server-side trả về, chỉ cần định nghĩa những trường thực sự cần thiết
- Thao tác thực hiện tương tự như thêm trường `PARAM` hay `BODY`, chỉ cần thêm tag `RESPONSE:`. Tóm lại API hoàn thiện sẽ như sau:

      // Other definition...
      POST [API_ENTRY]/record/lead/create
          PARAM: {
            someKey: 'value',
            anotherKey:  'value',
          }
          HEADER: {
            someKey: 'value',
            anotherKey:  'value',
          }
          BODY: {
            someKey: 'value',
            anotherKey:  'value',
          }
          RESPONSE: {
            someKey: 'value',
            anotherKey:  'value',
          }






