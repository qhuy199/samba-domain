## Áp dụng cho FAHASA (Test)
Server đặt IP 192.168.1.79/24 (Hoặc IP nào cũng được)

# Tải source về
```
mkdir -p /data/docker/builds
cd /data/docker/builds
yum -y install git
git clone https://github.com/qhuy199/samba-domain
cd samba-domain
```
# Tạo nơi lưu trữ (Nếu chưa có)
```
mkdir -p /data/docker/containers/samba/data
mkdir -p /data/docker/containers/samba/config/samba
```
# Deploy vào Docker Swarm
```
docker network create samba --scope swarm
docker stack deploy --compose-file docker-compose.yml samba
```
# Tạo account
```
docker exec -it samba bash
samba-tool user add test
```
# PC join domain
Đặt dns server trên PC là 192.168.1.79
Tiến hành join domain.
User: administrator
Pass: P@ssw0rd
