## Resource Control (vcpu,memory)
<img width="1919" height="929" alt="image" src="https://github.com/user-attachments/assets/5617816a-9a4b-4a4f-962b-0d63dedbba49" />
<img width="1919" height="931" alt="image" src="https://github.com/user-attachments/assets/4a25ca45-29d3-43f0-b91b-967873ad3ad0" />
### 🔹 CPU Hot Plug

CPU Hot Plug means I can **add CPU to the VM while it is running** without shutting it down.

> ⚠️ Note: It must be enabled before powering on the VM, and not all operating systems support it.

---

### 🔹 Reservation

Reservation means the **minimum guaranteed CPU** for a VM (measured in MHz).

> Even if there is high load on the host, this VM will always get at least this amount of CPU.

---

### 🔹 Limit

Limit is the **maximum CPU** that a VM can use.

> Even if there are free resources available, the VM will NOT exceed this limit.

---

### 🔹 Shares

Shares define the **priority of a VM compared to other VMs** when CPU resources are limited.

* High = 2000
* Medium = 1000
* Low = 500

---

### 🧠 How Shares Work

Shares only work during **CPU contention** (when resources are not enough).

If there is no load:

> All VMs can use CPU freely (shares have no effect)

If there is load:

> CPU is distributed based on the **ratio of shares**

---

### 📊 Example

Assume:

* VM1 = 1000 shares
* VM2 = 1000 shares
* VM3 = 2000 shares

Total shares = 4000

CPU distribution during contention:

* VM1 → 25%
* VM2 → 25%
* VM3 → 50%

> VM3 gets double the CPU compared to VM1 and VM2 because it has double shares.



