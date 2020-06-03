## Áp dụng cho FAHASA (Test)
Server đặt IP 192.168.1.79/24
Do có sử dụng --cap-add nên tạm thời deploy bằng Docker compose. Sẽ tìm cách đưa lên Swarm sau.

# [Cài đặt Docker Compose] Áp dụng cho Oracle Linux 7.7
```
curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```
# [Kiểm tra]
```
docker-compose --version
```
# [Tải source về]
```
mkdir -p /data/docker/builds
cd /data/docker/builds
yum -y install git
git clone https://github.com/qhuy199/samba-domain
cd samba-domain
```
# [Chạy file compose]
```
docker network create extnet
docker-compose up
```
# [Tạo account]
```
docker exec -it samba bash
samba-tool user add test
```
