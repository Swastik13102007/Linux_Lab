# 🧠 Linux Process Management – Assignment 7
## 🔹 1. Viewing All Processes

## 📑 1. ps aux

```bash
Explanation:
a → show processes for all users
u → show user/owner of process
x → show processes not attached to a terminal
Example Output:

```

![Image](./25_1.png)

---

## 🌲 2. Process Tree

command - pstree -p
![Image](./25_2.png)

👉 Shows parent-child process relationships.


## 📊 3. Real-Time Monitoring

command - top

![Image](./25_3.png)

👉 Press q to quit.

---

## ⚡ 4. Adjust Process Priority

### Start a process with low priority: 
nice -n 10 sleep 300 &

### Change Priority of a Running Process:
renice -n -5 -p 3050

![Image](./25_4.png)

![Image](./25_13.png)


👉 Now process runs with higher priority.
---

## 🔧 5. CPU Affinity (Bind Process to CPU Core)

command - taskset -cp 3050

![Image](./25_5.png)

---

## 📂 6. I/O Scheduling Priority

command - ionice -c 3 -p 3050

![Image](./25_6.png)

👉 Class 3 (idle) → Process only gets I/O when system is idle.

---

## 📑 7. File Descriptors Used by a Process

Command:
lsof -p 3050 | head -5


![Image](./25_7.png)
---

## 🐛 8. Trace System Calls of a Process

Command:
strace -p 3050

![Image](./25_8.png)

👉 Great for debugging  system calls and process behavior.

---

## 📡 9. Find Process Using a Port

Command:
sudo fuser -n tcp 8080

![Image](./25_9.png)

👉 PID 4321 is using port 8080.

---

## 📊 10. Per-Process Statistics

Command:
pidstat -p 3050 2 3

![Image](./25_10.png)

👉 Shows CPU usage every 2 seconds, 3 times.

---

## 🔐 11. Control Groups (cgroups) for Resource Limits

Create a new cgroup:
sudo cgcreate -g cpu,memory:/testgrou

![Image](./25_12.png)

---

## 🐛 12. Alternatives to nice / renice

```bash
1. chrt (Real-Time Scheduling)

Set real-time scheduling policies (FIFO or Round Robin).

sudo chrt -f 50 sleep 1000

chrt -p <pid>

2. ionice (I/O Priority Control)

ionice -c 2 -n 7 tar -czf backup.tar.gz /home

3. taskset (CPU Affinity)

taskset -c 1 firefox

4. Control Groups (cgroups)

sudo cgcreate -g cpu,memory:/lowprio
echo 20000 | sudo tee /sys/fs/cgroup/cpu/lowprio/cpu.cfs_quota_us
echo 200M   | sudo tee /sys/fs/cgroup/memory/lowprio/memory.limit_in_bytes
echo 1234 | sudo tee /sys/fs/cgroup/cpu/lowprio/cgroup.procs

5. systemd-run

systemd-run --scope -p CPUWeight=200 stress --cpu 4

6. schedtool

sudo schedtool -R -p 10 <pid>

```
---

## ✅ Summary Table

| Tool         | Focus                                 | Alternative to      |
|---------------|---------------------------------------|----------------------|
| **chrt**      | Real-time scheduling policies         | nice                 |
| **ionice**    | I/O priority control                  | (complementary)      |
| **taskset**   | CPU affinity control                  | (complementary)      |
| **cgroups**   | Fine-grained resource management      | nice (more powerful) |
| **systemd-run** | systemd + cgroups resource mgmt     | nice                 |
| **schedtool** | Custom scheduling policies            | nice                 |
``

--- 




