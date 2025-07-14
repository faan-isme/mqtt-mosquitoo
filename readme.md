
# Mqtt Broker

Ini merupakan mqtt broker berbasis mosquitoo yang berjalan di docker


## Deployment

Untuk menjalankan projek

```bash
  sudo docker-compose up -d
```
Untuk membuat password 

```bash
  sudo docker run --rm -v $(pwd)/password:/mosquitto/config eclipse-mosquitto mosquitto_passwd -b -c /mosquitto/config/passwd user1 "your_password_here"
```
ganti  "user1" dengan username, dan "your_password_here" dengan password
## Running Tests

testing untuk publish ke topik "test/topic"

```bash
  mosquitto_pub -h localhost -t "test/topic" -m "Hello from MQTT" -u "user1" -P "your_password_here"
```

testing untuk subscribe dari topik "test/topic"

```bash
  mosquitto_sub -h localhost -p 1883 -u "user1" -P "your_password_here" -t "test/topic"
```