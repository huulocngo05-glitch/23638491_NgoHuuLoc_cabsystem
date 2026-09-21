# CAB System – Domain & Subdomain Design

## 1. Mục tiêu

Tài liệu này trình bày cách phân rã Domain của hệ thống CAB thành các Subdomain theo nguyên tắc **High Cohesion** và thiết kế quan hệ giữa các Subdomain theo nguyên tắc **Loose Coupling**.

- **High Cohesion:** Mỗi Subdomain tập trung vào một nhóm nghiệp vụ có cùng mục tiêu và trách nhiệm.
- **Loose Coupling:** Các Subdomain chỉ trao đổi những thông tin hoặc kết quả nghiệp vụ cần thiết, hạn chế phụ thuộc vào cách xử lý và dữ liệu nội bộ của nhau.

---

## 2. Domain của hệ thống

Hệ thống CAB được phân thành 7 Domain chính:

1. Quản lý người dùng & định danh
2. Quản lý chuyến xe
3. Giá cước & thanh toán
4. Thông báo
5. Vận hành
6. Báo cáo & phân tích
7. Quản trị & kiểm soát

---

## 3. Phân rã Subdomain theo High Cohesion

### 3.1. Quản lý người dùng & định danh

| Subdomain | Trách nhiệm |
|---|---|
| **Quản lý định danh** | Đăng ký, đăng nhập và xác thực người dùng |
| **Quản lý khách hàng** | Quản lý thông tin và hồ sơ khách hàng |
| **Quản lý tài xế** | Quản lý thông tin và trạng thái làm việc của tài xế |
| **Quản lý phương tiện** | Quản lý thông tin phương tiện |
| **Quản lý quyền truy cập** | Quản lý vai trò và quyền truy cập |

### 3.2. Quản lý chuyến xe

| Subdomain | Trách nhiệm |
|---|---|
| **Đặt xe** | Tiếp nhận và quản lý yêu cầu đặt xe |
| **Phân công chuyến xe** | Tìm và phân công tài xế |
| **Quản lý chuyến xe** | Quản lý vòng đời và trạng thái chuyến xe |
| **Theo dõi chuyến xe** | Theo dõi trạng thái và vị trí chuyến xe |

### 3.3. Giá cước & thanh toán

| Subdomain | Trách nhiệm |
|---|---|
| **Quản lý giá cước** | Xác định và tính cước chuyến xe |
| **Quản lý thanh toán** | Xử lý thanh toán |
| **Quản lý giao dịch** | Ghi nhận và tra cứu giao dịch |

### 3.4. Thông báo

| Subdomain | Trách nhiệm |
|---|---|
| **Quản lý thông báo** | Quản lý và phát hành thông báo |
| **Gửi thông báo** | Gửi thông báo qua Push Notification, SMS và Email |

### 3.5. Vận hành

| Subdomain | Trách nhiệm |
|---|---|
| **Giám sát chuyến xe** | Giám sát hoạt động chuyến xe |
| **Hỗ trợ khách hàng** | Tiếp nhận và hỗ trợ khách hàng |
| **Xử lý sự cố** | Tiếp nhận và xử lý sự cố |
| **Tra cứu vận hành** | Tra cứu chuyến xe và giao dịch phục vụ vận hành |

### 3.6. Báo cáo & phân tích

| Subdomain | Trách nhiệm |
|---|---|
| **Báo cáo vận hành** | Báo cáo số chuyến, tỷ lệ hoàn thành và hủy |
| **Báo cáo tài chính** | Báo cáo doanh thu và thanh toán |
| **Phân tích hiệu quả tài xế** | Phân tích dữ liệu hoạt động của tài xế |

### 3.7. Quản trị & kiểm soát

| Subdomain | Trách nhiệm |
|---|---|
| **Cấu hình hệ thống** | Quản lý cấu hình hệ thống |
| **Quản lý phân quyền** | Quản lý vai trò và quyền truy cập |
| **Quản lý nhật ký** | Ghi nhận và tra cứu hoạt động hệ thống |
| **Kiểm soát bảo mật** | Kiểm soát và bảo vệ hệ thống |

---

## 4. Quy trình nghiệp vụ chính

```text
Quản lý định danh
        ↓
Quản lý khách hàng
        ↓
Đặt xe
        ↓
Phân công chuyến xe
        ↓
Quản lý chuyến xe
        ↓
Theo dõi chuyến xe
        ↓
Quản lý giá cước
        ↓
Quản lý thanh toán
        ↓
Quản lý giao dịch
```

Các Subdomain hỗ trợ:

```text
Đặt xe / Phân công / Quản lý chuyến xe / Thanh toán
                         ↓
                Quản lý thông báo
                         ↓
                   Gửi thông báo
```

```text
Quản lý chuyến xe
        ↓
Giám sát chuyến xe
        ↓
Xử lý sự cố
```

```text
Quản lý chuyến xe / Quản lý thanh toán / Quản lý tài xế
                         ↓
                Báo cáo & phân tích
```

```text
Các hoạt động nghiệp vụ
          ↓
   Quản lý nhật ký
```

---

## 5. Quan hệ giữa các Subdomain theo Loose Coupling

### 5.1. Định danh → Khách hàng / Tài xế

```text
Quản lý định danh
       │
       ├── identity_id ──→ Quản lý khách hàng
       │
       └── identity_id ──→ Quản lý tài xế
```

Chỉ trao đổi thông tin định danh cần thiết, không phụ thuộc vào dữ liệu nội bộ của Subdomain quản lý định danh.

### 5.2. Khách hàng → Đặt xe

```text
Quản lý khách hàng
        │
        └── customer_id ──→ Đặt xe
```

Subdomain Đặt xe chỉ cần xác định khách hàng thực hiện yêu cầu.

### 5.3. Đặt xe → Phân công chuyến xe

```text
Đặt xe
  │
  └── booking_id + thông tin yêu cầu ──→ Phân công chuyến xe
```

Phân công chuyến xe chỉ nhận thông tin cần thiết để thực hiện điều phối.

### 5.4. Tài xế / Phương tiện → Phân công chuyến xe

```text
Quản lý tài xế ────────┐
                       ├──→ Phân công chuyến xe
Quản lý phương tiện ───┘
```

Thông tin trao đổi có thể gồm `driver_id`, `vehicle_id` và trạng thái sẵn sàng.

### 5.5. Phân công → Quản lý chuyến xe

```text
Phân công chuyến xe
        │
        └── trip_id + driver_id ──→ Quản lý chuyến xe
```

### 5.6. Quản lý chuyến xe → Theo dõi chuyến xe

```text
Quản lý chuyến xe
        │
        └── trip_id + trạng thái/vị trí ──→ Theo dõi chuyến xe
```

### 5.7. Chuyến xe → Giá cước → Thanh toán → Giao dịch

```text
Quản lý chuyến xe
        │
        └── thông tin chuyến hoàn thành
                    ↓
             Quản lý giá cước
                    │
                    └── số tiền cần thanh toán
                              ↓
                     Quản lý thanh toán
                              │
                              └── kết quả thanh toán
                                        ↓
                               Quản lý giao dịch
```

Mỗi Subdomain chỉ cung cấp kết quả nghiệp vụ cần thiết cho Subdomain tiếp theo.

### 5.8. Các Subdomain nghiệp vụ → Thông báo

```text
Đặt xe ───────────────┐
Phân công chuyến xe ──┤
Quản lý chuyến xe ────┤
Quản lý thanh toán ───┤
                      ↓
              Quản lý thông báo
                      ↓
                Gửi thông báo
```

Các Subdomain nghiệp vụ không phụ thuộc trực tiếp vào Push Notification, SMS hoặc Email. Chúng chỉ phát sinh sự kiện nghiệp vụ, còn Subdomain Thông báo chịu trách nhiệm xử lý việc gửi.

Ví dụ:

```text
BookingCreated
DriverAssigned
TripStatusChanged
PaymentCompleted
```

### 5.9. Chuyến xe → Vận hành

```text
Quản lý chuyến xe
        ↓
Giám sát chuyến xe
        ↓
Xử lý sự cố
```

Vận hành sử dụng thông tin chuyến xe để giám sát và xử lý nhưng không sở hữu vòng đời chuyến xe.

### 5.10. Dữ liệu nghiệp vụ → Báo cáo & phân tích

```text
Quản lý chuyến xe ─────┐
Quản lý thanh toán ────┼──→ Báo cáo & phân tích
Quản lý tài xế ────────┘
```

Báo cáo & phân tích chỉ nhận dữ liệu cần thiết để tổng hợp, không phụ thuộc vào cách các Subdomain nguồn lưu trữ và xử lý dữ liệu.

### 5.11. Hoạt động nghiệp vụ → Quản lý nhật ký

```text
Các hoạt động nghiệp vụ
          ↓
   Quản lý nhật ký
```

Quản lý nhật ký nhận các sự kiện hoạt động cần ghi nhận, thay vì truy cập trực tiếp dữ liệu nội bộ của từng Subdomain.

---

## 6. Sơ đồ quan hệ tổng thể

```text
                         ┌─────────────────────┐
                         │ QUẢN LÝ ĐỊNH DANH  │
                         └─────────┬───────────┘
                                   │
                    ┌──────────────┴──────────────┐
                    ↓                             ↓
          ┌─────────────────┐           ┌─────────────────┐
          │ QUẢN LÝ         │           │ QUẢN LÝ         │
          │ KHÁCH HÀNG      │           │ TÀI XẾ          │
          └────────┬────────┘           └────────┬────────┘
                   │                             │
                   │                             ↓
                   │                    ┌─────────────────┐
                   │                    │ QUẢN LÝ         │
                   │                    │ PHƯƠNG TIỆN     │
                   │                    └────────┬────────┘
                   │                             │
                   └──────────────┬──────────────┘
                                  ↓
                         ┌─────────────────┐
                         │     ĐẶT XE      │
                         └────────┬────────┘
                                  ↓
                         ┌─────────────────┐
                         │ PHÂN CÔNG       │
                         │ CHUYẾN XE       │
                         └────────┬────────┘
                                  ↓
                         ┌─────────────────┐
                         │ QUẢN LÝ         │
                         │ CHUYẾN XE       │
                         └───────┬─┬───────┘
                                 │ │
                    ┌────────────┘ └─────────────┐
                    ↓                            ↓
          ┌─────────────────┐          ┌─────────────────┐
          │ THEO DÕI        │          │ QUẢN LÝ         │
          │ CHUYẾN XE       │          │ GIÁ CƯỚC        │
          └─────────────────┘          └────────┬────────┘
                                                ↓
                                       ┌─────────────────┐
                                       │ QUẢN LÝ         │
                                       │ THANH TOÁN      │
                                       └────────┬────────┘
                                                ↓
                                       ┌─────────────────┐
                                       │ QUẢN LÝ         │
                                       │ GIAO DỊCH       │
                                       └─────────────────┘
```

---

## 7. Nguyên tắc thiết kế

| Nguyên tắc | Cách áp dụng |
|---|---|
| **High Cohesion** | Mỗi Subdomain tập trung vào một mục tiêu nghiệp vụ rõ ràng |
| **Loose Coupling** | Chỉ trao đổi thông tin/kết quả nghiệp vụ cần thiết |
| **Không truy cập chéo CSDL** | Không để Subdomain đọc trực tiếp dữ liệu nội bộ của Subdomain khác |
| **Giảm phụ thuộc** | Ưu tiên trao đổi ID, trạng thái, kết quả hoặc sự kiện nghiệp vụ |
| **Tách trách nhiệm** | Subdomain không thực hiện thay trách nhiệm của Subdomain khác |
| **Event-driven cho chức năng hỗ trợ** | Thông báo, nhật ký và báo cáo có thể nhận sự kiện từ nghiệp vụ chính |

---

## 8. Kết luận

Thiết kế Subdomain của CAB System được thực hiện theo hai nguyên tắc:

**High Cohesion:** Các chức năng có cùng mục tiêu và trách nhiệm nghiệp vụ được gom vào cùng một Subdomain.

**Loose Coupling:** Các Subdomain chỉ giao tiếp thông qua thông tin hoặc kết quả nghiệp vụ cần thiết, hạn chế phụ thuộc trực tiếp vào dữ liệu và cách xử lý nội bộ của nhau.

Luồng nghiệp vụ cốt lõi:

```text
Quản lý định danh
→ Quản lý khách hàng
→ Đặt xe
→ Phân công chuyến xe
→ Quản lý chuyến xe
→ Theo dõi chuyến xe
→ Quản lý giá cước
→ Quản lý thanh toán
→ Quản lý giao dịch
```

Các Subdomain **Thông báo, Vận hành, Báo cáo & phân tích và Quản lý nhật ký** đóng vai trò hỗ trợ và liên kết với các Subdomain nghiệp vụ thông qua thông tin hoặc sự kiện cần thiết, giúp giảm sự phụ thuộc giữa các thành phần của hệ thống.
