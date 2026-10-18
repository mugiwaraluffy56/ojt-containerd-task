Scenario

You are a junior DevOps engineer. Your team has developed a small web application, but it needs to be containerized and deployed to Kubernetes.

Your task is to build the application, deploy it, troubleshoot a few failures, and verify that it works correctly.

You may use AI tools and official documentation, but you must understand and explain the commands you execute.

Task 1: Build the Docker Image (15 points)

Create a simple Python or Node.js web application.

The application should expose:

/ — returns a welcome message.

/health — returns a healthy status.

Write a Dockerfile and build an image named student-app:v1.

Run the container and test both endpoints.

Show the output of docker images and docker ps.

Task 2: Deploy to Kubernetes (25 points)

Create a local Kubernetes cluster using Minikube or kind.

Make the Docker image available to the Kubernetes nodes.

Create a Deployment with two replicas.

Create a Service to expose the application.

Verify that both pods are running and that the application is accessible.

Task 3: Explore containerd (20 points)

Find out which container runtime your Kubernetes node uses.

Use crictl or ctr to list the available images.

Find the application container running inside the Kubernetes node.

Explain why an image built with Docker may not automatically be available to Kubernetes.

Explain the difference between Docker, containerd, and Kubernetes.

Capture the commands and their outputs.

Task 4: Troubleshooting Challenge (25 points)

Complete these three exercises, one at a time.

Problem A — Image error

Change the Deployment to use an image tag that does not exist.

Identify the pod's status.

Find the cause using kubectl describe pod.

Fix the image reference and verify recovery.

Problem B — Application health

Configure an incorrect health-check path in the Deployment.

Observe what happens to the pod.

Find the problem using pod events and logs.

Correct the health-check configuration.

Problem C — Service connectivity

Change the Service's target port to an incorrect value.

Test the application through the Service.

Identify the port mismatch.

Fix the configuration and test again.

Task 5: Submission (15 points)

Submit a GitHub repository containing:

Application source code.

Dockerfile.

Kubernetes Deployment and Service YAML files.

Commands and screenshots showing containerd inspection.

A short explanation of how you diagnosed and fixed each problem.

A README explaining how someone else can run your project.

Evaluation Criteria

Category

Points

Docker image and application

15

Kubernetes deployment

25

containerd inspection

20

Troubleshooting

25

Documentation and explanations

15

Total

100