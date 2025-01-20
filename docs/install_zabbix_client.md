#  Cài đặt zabbix client, và hướng dẫn kết nối zabbix client với zabbix server  
## Cài đặt ZABBIX version 6.4 trên ubuntu 20.04
- Môi trường
  chuẩn bị ubunu server version 20.04
## Cài đặt
- Tham khảo hướng dẫn trên trang web chính thức của zabbix, tương tự như zabbix server, nhưng đến đoạn cài zabbx thì chúng ta chỉ cần cài zabbix client
[Truy cập zabbix download](https://www.zabbix.com/download?zabbix=6.4&os_distribution=ubuntu&os_version=20.04&components=server_frontend_agent&db=mysql&ws=apache)

Trên server cài đặt zabbix client, khi cài đặt xong chúng ta cần phải sửa một một chút cấu hình để cho zabbix server sẽ nhận được thông tin mà zabbix client thu thập từ phía server zabbix-client: các tham số về server, server active và hostname

![Hình 1](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/zabbix_client_1.png?raw=true)  

Sau khi thay đổi config xong chúng tiếp tục restart lại zabbix client bằng câu lệnh 

```bash
systemctl restart zabbix-agent.service
```
Sau khi restart xong chúng ta có thể kiểm tra lại trạng thái xem zabbix agent đã hoạt động được chưa
- Tiếp theo chúng ta sẽ tiến hành thiếp lập kết nối với zabbix server trên màn hình dashboard để tiến hành lấy dữ liệu thu thập zabbix client
Chúng vào vào host trong phần data colection để tiến hành tạo host mới

![Hình 2](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/zabbix-client_2.png?raw=true)    

Nhớ thêm cả templete nữa nhé, không thì có thể update lại sau 

![Hình 3](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/zabbix-client_3.png?raw=true)  

