# minikube-mongodb-with-mongoexpress

```markdown
# Kubernetes MongoDB and WebApp Deployment

This project demonstrates how to deploy a MongoDB database and a web application using Kubernetes. The configurations include secrets, config maps, and deployments for a complete setup.

## Prerequisites

- **Minikube**: Ensure Minikube is installed on your machine. [Minikube Installation Guide](https://minikube.sigs.k8s.io/docs/start/)
- **Visual Studio Code**: Ensure you have Visual Studio Code installed with the necessary extensions for Kubernetes and Docker.
- **WSL (Windows Subsystem for Linux)**: Follow the [WSL Installation Guide](https://docs.microsoft.com/en-us/windows/wsl/install) to set up WSL on your machine.

## Project Structure

```
project-name/
│
├── secret.yaml
├── configmap.yaml
├── mongo-app.yaml
├── webapp-deployment.yaml
├── README.md
└── .gitignore
```

## Configuration Files

### Secrets

Create Kubernetes secrets to store sensitive data like usernames and passwords. These secrets are encoded in base64 and stored in a `secret.yaml` file. For more information on how to create secrets in Kubernetes, refer to the [Kubernetes documentation](https://kubernetes.io/docs/concepts/configuration/secret/).

### ConfigMaps

ConfigMaps are used to store non-sensitive data such as configuration settings. These settings are stored in a `configmap.yaml` file. For more information on ConfigMaps, refer to the [Kubernetes documentation](https://kubernetes.io/docs/concepts/configuration/configmap/).

### MongoDB Deployment

Deploy MongoDB using a deployment configuration file `mongo-app.yaml`. This file includes environment variables for the MongoDB root username and password, which are sourced from the secrets.

### WebApp Deployment

Deploy the web application using a deployment configuration file `webapp-deployment.yaml`. This configuration is similar to the MongoDB deployment but includes environment variables specific to the web application, such as database connection details sourced from the ConfigMap.

## Steps to Deploy

1. **Install Minikube and WSL**: Ensure Minikube and WSL are installed and configured on your machine.
2. **Create Secrets and ConfigMaps**: Create the necessary secrets and config maps using the provided YAML files.
3. **Deploy MongoDB**: Apply the `mongo-app.yaml` file to deploy MongoDB.
4. **Deploy WebApp**: Apply the `webapp-deployment.yaml` file to deploy the web application.

## Commands

- To create secrets:
  ```sh
  kubectl apply -f secret.yaml
  ```

- To create config maps:
  ```sh
  kubectl apply -f configmap.yaml
  ```

- To deploy MongoDB:
  ```sh
  kubectl apply -f mongo-app.yaml
  ```

- To deploy WebApp:
  ```sh
  kubectl apply -f webapp-deployment.yaml
  ```

## Important Notes

- Ensure the environment variables in your deployment files are correctly set to reference the secrets and config maps.
- Modify the configuration files as necessary to fit your specific requirements.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

This README provides an overview of the project, explains the purpose of each configuration file, and includes instructions on how to deploy the application using Kubernetes.
