# Linux Virtualization Assignment

## Working with Multipass

### Installation of Multipass
```bash
sudo snap install multipass
```

### Creating and Managing Instances
```bash
multipass launch --name my-vm
multipass list
multipass shell my-vm
```

### Study Materials


### Screenshots
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/Screenshot%202025-02-16%20185224.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/Screenshot%202025-02-16%20185348.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/Screenshot%202025-02-16%20185838.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/Screenshot%202025-02-16%20191250.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/Screenshot%202025-02-16%20191340.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/Screenshot%202025-02-16%20191410.png)
### Challenges Faced


## Part 3: Exploring LXD

### Installing LXD
```bash
sudo snap install lxd
lxd init
```

### Creating and Managing Containers
```bash
lxc launch ubuntu:22.04 my-container
lxc list
lxc exec my-container -- bash
```

### Study Materials


### Screenshots
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/a.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/b.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/c.png)
### Challenges Faced


## Part 4: How to Stick Apps with Docker

### Installing Docker
```bash
sudo apt update
sudo apt install docker.io
sudo systemctl enable --now docker
```

### Running a Docker Container
```bash
docker run -d --name my-nginx -p 8080:80 nginx
```

### Managing Containers
```bash
docker ps
docker stop my-nginx
docker rm my-nginx
```

### Study Materials


### Screenshots
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/d.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/e.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/f.png)
### Challenges Faced


## Part 5: Snaps for Self-Contained Applications

### Installing Snapcraft
```bash
sudo snap install snapcraft --classic
```

### Creating a Snap Application
```bash
mkdir my-snap
cd my-snap
snapcraft init
```

### Building and Packing the Snap
```bash
snapcraft
```

### Study Materials


### Screenshots
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/1.png)
![](https://github.com/FawazSalman/linux-management/blob/main/virtualization/images/2.png)
### Challenges Faced


## Summary
Provide a reflection on the overall learning experience, key takeaways, and how virtualization, LXD, Docker, and Snapcraft contribute to modern Linux systems.

*(Insert summary screenshots if applicable)*

