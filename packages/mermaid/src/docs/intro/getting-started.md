%% Định nghĩa các nhóm biến số quản lý (Trục dọc)
    subgraph "CHỨC NĂNG QUẢN LÝ (MANAGEMENT FUNCTIONS)"
    P(<b>LẬP KẾ HOẠCH</b><br/>(PLANNING))
    O(<b>TỔ CHỨC</b><br/>(ORGANIZING))
    L(<b>CHỈ ĐẠO</b><br/>(LEADING))
    C(<b>KIỂM TRA - ĐÁNH GIÁ</b><br/>(CONTROLLING))
    end

    %% Định nghĩa mô hình CIPO (Trục ngang)
    subgraph "MÔ HÌNH CIPO (CIPO MODEL)"
    Ctx(<b>BỐI CẢNH</b><br/>(CONTEXT)<br/>Nhu cầu thị trường y tế<br/>Chính sách giáo dục)
    Inp(<b>ĐẦU VÀO</b><br/>(INPUT)<br/>Chương trình ESP<br/>Giảng viên<br/>Cơ sở vật chất)
    Pro(<b>QUÁ TRÌNH</b><br/>(PROCESS)<br/>Hoạt động giảng dạy<br/>Phương pháp sư phạm)
    Out(<b>ĐẦU RA</b><br/>(OUTPUT)<br/>Năng lực ngôn ngữ<br/>Khả năng ứng dụng lâm sàng)
    end

    %% Định nghĩa các mối liên hệ cụ thể (Mục 2.3 trong bài)
    Ctx -.->|Phân tích| P
    P ==>|Cụ thể hóa| Inp
    P -.->|Xác lập chuẩn| Out
    Inp -.->|Phân bổ| O
    O ==>|Vận hành| Pro
    L ==>|Điều phối| Pro
    Pro -.->|Đối soát| C
    Out ==>|Cung cấp dữ liệu| C
    C -.->|Phản hồi & Cải tiến| P

    %% Thêm mũi tên phản hồi hệ thống
    C -.Feedback.-> P

    %% Định nghĩa kiểu dáng
    classDef CIPO fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#1565c0;
    classDef MGT fill:#fff9c4,stroke:#fbc02d,stroke-width:2px,color:#fbc02d;
    classDef Connect stroke-width:1.5px,stroke-dasharray: 5 5;
    classDef Implies stroke-width:3px,color:#000;

    class Ctx,Inp,Pro,Out CIPO;
    class P,O,L,C MGT;
    linkStyle 0,3,5,7,9,10 class Connect;
    linkStyle 1,4,6,8 class Implies;
