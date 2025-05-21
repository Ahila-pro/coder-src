# image : codercom/code-server:latest
# What is it?
This is an official Docker image maintained by coder.com, which runs code-server — a web-based version of Visual Studio Code.

# What does it do?
It runs VS Code in a server mode that you can access from a browser. You get the full VS Code experience remotely, without needing to install VS Code locally.

# Why use this image?

It bundles everything needed to run VS Code remotely inside a container.

It’s regularly updated and maintained by the official team.

Supports extensions, settings sync, terminal, file editing, debugging — just like the desktop VS Code.

Lightweight compared to running a full desktop environment.

# How does it work?
The container starts a web server on port 8080 by default, serving the VS Code UI. You connect to it through a browser, log in (usually via a password), and code remotely.

# Key points for Kubernetes deployment:
The container exposes port 8080 — the port you’ll access via your Kubernetes Service.

You can set environment variables like PASSWORD to secure access.

It's ideal for cloud/dev environments where you want VS Code accessible anywhere.

# Steps:
1. minikube kubectl -- apply -f csdeployment.yaml
2. minikube kubectl -- apply -f csservice.yaml
3. minikube service codeserver-service --url
    O/P -->  http://127.0.0.1:53489  (Expose this in browser)
4. minikube tunnel