# Computer Control with Cursor

This project provides a Docker container with a virtual desktop environment accessible through a web browser, with proper cursor support.

## Prerequisites

- Docker installed on your system
- A web browser
- Git (for cloning the repository)

## Installation and Running

1. Clone the repository:
```bash
git clone https://github.com/agentbryce2025/computer_control_with_cursor.git
cd computer_control_with_cursor
```

2. Build the Docker image:
```bash
docker build -t computer-control-cursor .
```

3. Run the container:
```bash
docker run -d \
  --name computer-control \
  -p 8080:8080 \
  --shm-size=1g \
  computer-control-cursor
```

4. Access the virtual desktop:
   - Open your web browser
   - Navigate to `http://localhost:8080`
   - You should see the virtual desktop environment

## Important Notes

- The container exposes port 8080 for web access
- The virtual desktop resolution is set to 1024x768
- The environment uses IceWM as the window manager
- Cursor support is enabled using the DMZ-White theme

## Stopping the Container

To stop the container:
```bash
docker stop computer-control
```

To remove the container:
```bash
docker rm computer-control
```

## Troubleshooting

If you encounter issues:

1. Check container logs:
```bash
docker logs computer-control
```

2. Verify the container is running:
```bash
docker ps
```

3. If the web interface isn't responding, ensure port 8080 isn't being used by another application

4. For cursor issues, try refreshing the browser page