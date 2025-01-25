# JBang Catalog for Jakarta EE and Payara Tools

This repository contains a **JBang catalog** that simplifies the use of **Payara Micro** and **Payara Cloud CLI** (`pcl`) for Jakarta EE development. With this catalog, you can quickly run Payara Micro for local development and deploy applications to Payara Cloud using JBang.

---

## **Getting Started**

### **1. Add the Catalog**
To use the catalog, add it to your JBang configuration with the following command:

```bash
jbang catalog add jakarta https://raw.githubusercontent.com/your-repo/jbang-catalog/main/jbang-catalog.json
```

This will register the catalog and make the aliases available for use.

---

### **2. Available Aliases**

#### **Payara Micro**
Run Payara Micro to deploy and test Jakarta EE applications locally:
```bash
jbang micro
```

**Common Options**:
- Deploy a WAR file:
  ```bash
  jbang micro --deploy my-app.war
  ```
- Change the HTTP port:
  ```bash
  jbang micro --deploy my-app.war --port 9090
  ```
- Enable request tracing:
  ```bash
  jbang micro --deploy my-app.war --enableRequestTracing
  ```

#### **Payara Cloud CLI (`pcl`)**
Manage Payara Cloud namespaces and deploy applications:
```bash
jbang pcl
```

**Common Commands**:
- List namespaces:
  ```bash
  jbang pcl namespace list
  ```
- Deploy an application:
  ```bash
  jbang pcl deploy my-app my-app.war
  ```

---

### **3. Verify the Aliases**
To see all available aliases, run:
```bash
jbang alias list
```

You should see `micro` and `pcl` in the output.

---

## **Catalog Contents**

The `jbang-catalog.json` file defines the following aliases:

```json
{
  "catalogs": {},
  "aliases": {
    "micro": {
      "script-ref": "fish.payara.extras:payara-micro:6.2024.10",
      "description": "Payara Micro is an embedded Jakarta EE runtime for running WAR files."
    },
    "pcl": {
      "repositories": ["payara=https://nexus.payara.fish/repository/payara-artifacts"],
      "script-ref": "fish.payara.cloud:pcl:1.1.0",
      "description": "Payara Cloud CLI for managing namespaces and applications."
    }
  },
  "templates": {}
}
```

---

## **Why Use This Catalog?**

- **Simplified Setup**: No need to manually configure Payara Micro or the Payara Cloud CLI.
- **Consistency**: Ensures everyone on your team uses the same versions of tools.
- **Portability**: Run Jakarta EE applications locally or deploy them to the cloud with ease.
- **Speed**: Get started quickly with pre-configured aliases.

---

## **Contributing**

If you’d like to add more tools or improve the catalog, feel free to open a pull request! Here’s how:

1. Fork the repository.
2. Make your changes to `jbang-catalog.json`.
3. Submit a pull request with a description of your changes.

---


