# Cài đặt granfana và cấu hình plugin zabbix để granfa có thể lấy dữ liệu từ zabbix và vẽ biểu đồ
## Hướng dẫn cài đặt granfana trên ubuntu version 20.04
Chạy những dòng lệnh dưới đây 

```bash
apt install -y gnupg2 curl software-properties-common
curl -fsSL https://packages.grafana.com/gpg.key|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/grafana.gpg
add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
apt-get install grafana -y
grafana-server -v
systemctl start grafana-server
systemctl enable grafana-server
systemctl status grafana-server
```
Sau khi chạy xong thì chúng ta có thể đăng nhập vào giao diện của granfana với (địa chỉ IP của server:3000) cùng với tên đăng nhập và mật khẩu mặc định là admin/admin  
Chúng ta đã đăng nhập vào giao diện dashboard của grafana và chúng ta sẽ thấy hình như sau  

![Hình 1](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/granfana_1.png?raw=true)  

Tiếp theo chúng ta sẽ add plugin của zabbix vào granfana, tìm kiếm zabbix, install và enable zabbix

![Hình 2](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/granfana_2.png?raw=true)  


![Hình 3](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/granfana_3.png?raw=true)



Sau khi đã thêm plugin xong rồi chúng ta tiếp tục thêm data source là zabbix vào theo các hình dưới đây

![Hình 4](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/granfana_4.png?raw=true)  

Chúng ta để ý một chút ở phần URL nếu chưa add host vào thì chúng ta cứ dùng địa chỉ IP như bình thường

![Hình 5](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/granfana_5.png?raw=true)  

Phần nhập user và password chính là user và password dành cho zabbix

Sau Khi được như vậy, chúng ta tiến hành lưu lại và test, kết quả hiển thị như trên màn hình là thành công 


![Hình 6](https://github.com/haituan1703/Install_zabbix_draw_granfana_charts_from_zabbix_telegram_notifications/blob/main/docs/image/granfana_6.png?raw=true)

- Tiếp tục chúng ta sẽ tạo dashboard và chúng ta sẽ thử vẽ một biểu đồ dựa vào data source của zabbix




