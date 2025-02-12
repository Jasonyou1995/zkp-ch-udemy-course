Here’s how you can adapt these commands for macOS:

Local Run

On macOS, you need to install Rust and the protobuf-compiler using Homebrew:

brew install rust protobuf

Docker

Since macOS uses a virtualized environment for Docker, the commands remain mostly the same.

Build the Docker container:

docker-compose build zkpserver

Run the Docker container:

docker-compose run --rm zkpserver

Start the server inside the container:

Once the container starts, you’ll see a remote shell. Run:

cargo run --bin server --release

Connect to the running container from a new terminal:
	1.	List running containers:

docker container ls

You should see something like:

CONTAINER ID   IMAGE                  COMMAND   CREATED         STATUS         PORTS     NAMES
e84736012f9a   zkp-course-zkpserver   "bash"    X minutes ago   Up X minutes             zkp-course_zkpserver_run_b1f3fa2cd94a


	2.	Attach to the running container:

docker exec -it e84736012f9a /bin/bash



Run the client inside the container:

cargo run --bin client --release

Notes for macOS:
	•	If you face issues with file permissions in Docker, you may need to adjust volume mounts (:cached or :delegated options).
	•	Docker on macOS runs inside a Linux VM, so performance may slightly differ.
	•	Ensure docker and docker-compose are installed via Homebrew:

brew install docker docker-compose


	•	You may need to start Docker Desktop (open -a Docker) before running these commands.

Let me know if you need adjustments! 🚀