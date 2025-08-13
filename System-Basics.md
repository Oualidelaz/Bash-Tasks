## 1. Distribution Information

- display your Linux distribution name and version :

```bash
echo "$(cat /etc/os-release | awk 'NR==1') - $(cat /etc/os-release | awk 'NR==3')"
````

## 2. User Information

- get current username and user ID:

```bash
echo "username: $(id -un), id: $(id -u)"
```

## 3. Network Information

- hostname and IP address:

```bash
echo "hostname: $(hostname), address: $(hostname -I | awk '{print $1}')"
```

## 4. Environment Variables

- list all environment variables:

```bash
env | awk -F '=' '{print $1}'
```

## 5. System Type Check

- verify if the system is running Linux:

```bash
uname
```

## 6. System Uptime

- check how long the system has been running:

```bash
uptime
```

## 7. CPU Information

- get CPU model and core count:

```bash
echo "Model: $(cat /proc/cpuinfo | grep -i "model name" -m 1 | awk -F ': ' '{print $2}'), Cores: $(cat /proc/cpuinfo | grep -i "cpu cores" -m 1 | awk -F ': ' '{print $2}')"
```

## 8. Memory Information

- display RAM usage in human-readable format:

```bash
echo "Total Ram Size: $(free -h | grep "Mem" | awk '{print $2}'), available: $(free -h | grep "Mem" | awk '{print $4}')"
```

## 9. Architecture Information

- determine system architecture:

```bash
uname -m
```

## 10. System Monitor

- real-time system resource monitoring:

```bash
top
```
