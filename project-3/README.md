# Project 3: Notes Storage Application

## Objective

Learn Docker persistent storage using Bind Mounts and Volumes.

## Technologies Used

* Docker
* Ubuntu Image

## Project Structure

```text
project-3/
├── note1.txt
├── note2.txt
├── note3.txt
└── README.md
```

## Part 1: Bind Mount

### Run Container with Bind Mount

```bash
docker run -it -v "C:\Users\devopselearningpractice\project-3:/opt/data" ubuntu bash
```

### Verify Files

```bash
cd /opt/data
ls
cat note1.txt
```

### Create a New File

```bash
cat > note4.txt
```

Example content:

```text
Docker Persistence Test

This file was created inside the container.
```

Press:

```text
Ctrl + D
```

### Verify File

```bash
cat note4.txt
```

### Recreate Container

After removing the container, start a new one with the same bind mount and verify that `note4.txt` still exists.

---

## Part 2: Docker Volume

### Create Volume

```bash
docker volume create notes-volume
```

### Run Container Using Volume

```bash
docker run -it -v notes-volume:/opt/data ubuntu bash
```

### Create File Inside Volume

```bash
cat > volume-note.txt
```

Example content:

```text
This file is stored in a Docker volume.
```

Press:

```text
Ctrl + D
```

### Verify File

```bash
cat volume-note.txt
```

### Recreate Container

Remove the container and create a new container using the same volume.

Verify:

```bash
cd /opt/data
ls
```

The file should still be available.

---

## Concepts Learned

### Bind Mount

* Uses a host machine directory.
* Files are visible on the host.
* Changes are synchronized between host and container.

### Docker Volume

* Managed by Docker.
* Data persists independently of containers.
* Commonly used for databases and application storage.

## Skills Gained

* Docker Storage
* Bind Mounts
* Docker Volumes
* Data Persistence
* Container Recreation Testing

## Conclusion

Successfully demonstrated Docker persistent storage using both Bind Mounts and Volumes. Verified that data remains available after container deletion and recreation.
