# Cài đặt granfana và cấu hình plugin zabbix để granfa có thể lấy dữ liệu từ zabbix và vẽ biểu đồ
## Hướng dẫn cài đặt granfana trên ubuntu version 20.04
Chúng chạy những dòng lệnh dưới đây 

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
