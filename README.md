# 3-Tier DevSecOps Project

This repository contains a simple Node.js API and a React client used for a user management demo. Follow the steps below to get the project running locally.

## Setup

1. Install Node.js (version 18 or later is recommended).
2. Install dependencies for both the API and client:

   ```bash
   cd api && npm install
   cd ../client && npm install
   ```

3. Start the API server:

   ```bash
   cd api
   npm start
   ```

4. In a separate terminal, start the React client:

   ```bash
   cd client
   npm start
   ```

5. Open `http://localhost:3000` in your browser to use the application.


if we use kind cluster --> After deployment follow this steps.

1.  kind get clusters

2.  kind get kubeconfig --name kind-cluster > ~/.kube/config

3.  kubectl config get-contexts

   CURRENT   NAME                CLUSTER             AUTHINFO            NAMESPACE
   *         kind-kind-cluster   kind-kind-cluster   kind-kind-cluster

4.  kubectl config current-context

    kind-kind-cluster

6. kubectl get all -n XXXXXXX

7. please farward the port with the following command.

   kubectl port-forward -n XXXXXXXX service/frontend-service 8082:80 --address=0.0.0.0 &
