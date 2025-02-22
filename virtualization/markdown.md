# Linux Virtualization Assignment

## Part 1: Introduction to Virtualization Concepts

### Overview
Provide a brief summary of virtualization concepts, including types (full virtualization, para-virtualization, containerization) and their benefits.

### Study Materials
*(Insert screenshots of study materials here)*

### Challenges Faced
*(Describe any difficulties encountered in understanding virtualization concepts and how they were resolved.)*

## Part 2: Working with Multipass

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
*(Describe any issues encountered during installation or usage of Multipass and solutions applied.)*

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
*(Insert screenshots of installation and container management commands here)*

### Challenges Faced
*(Describe any problems faced with LXD and how they were resolved.)*

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
*(Insert screenshots of Docker installation and commands execution here)*

### Challenges Faced
*(Describe any issues faced while working with Docker and their solutions.)*

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
*(Insert screenshots of Snapcraft installation, configuration, and packing process here)*

### Challenges Faced
*(Describe any challenges faced while working with Snapcraft and solutions applied.)*

## Summary
Provide a reflection on the overall learning experience, key takeaways, and how virtualization, LXD, Docker, and Snapcraft contribute to modern Linux systems.

*(Insert summary screenshots if applicable)*

