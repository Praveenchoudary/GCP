

# 🔐 Day 03 – IAM in Google Cloud Platform (GCP)

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b4e71ca8-1a7c-4bf2-b034-11cc25bf0263" />


## 🌐 What is IAM?

**IAM (Identity and Access Management)** in **Google Cloud Platform (GCP)** is used to control **who can access what resources and what actions they can perform**.

IAM helps organizations manage **permissions securely** so that users only access the resources they need.

Example:

* 👨‍💻 A DevOps engineer can create VMs
* 📊 A finance team member can view billing
* 🔒 A security team can manage policies

This ensures **secure and controlled access** to cloud resources.

---

# 🧩 Components of IAM

IAM mainly consists of **three key components**:

```text
Member → Role → Resource
```

| Component   | Description                          |
| ----------- | ------------------------------------ |
| 👤 Member   | The user or entity requesting access |
| 🛡️ Role    | The permissions granted              |
| ☁️ Resource | The cloud resource being accessed    |

---

# 👤 1. Member (Who?)

A **Member** is the identity that can access resources.

Examples:

* 👤 User (person with Gmail or company email)
* 👥 Google Group
* 🤖 Service Account
* 🌐 Domain

Example members:

```text
user:praveen@gmail.com
group:devops-team@company.com
serviceAccount:myapp@project-id.iam.gserviceaccount.com
```

---

# 🛡️ 2. Role (What can they do?)

A **Role** is a collection of permissions.

Instead of giving permissions one by one, GCP groups them into **roles**.

### Types of IAM Roles

#### 🟢 Basic Roles

| Role   | Permission              |
| ------ | ----------------------- |
| Owner  | Full control of project |
| Editor | Can modify resources    |
| Viewer | Can only view resources |

---

#### 🔵 Predefined Roles

Google provides predefined roles for specific services.

Examples:

* Compute Admin
* Storage Admin
* Kubernetes Engine Admin
* Cloud SQL Admin

Example:

```text
roles/compute.admin
roles/storage.admin
```

---

#### 🟣 Custom Roles

Organizations can create **custom roles** with specific permissions.

Example:

A role that only allows:

* Start VM
* Stop VM

But **cannot delete VM**.

---

# ☁️ 3. Resource (Where?)

A **Resource** is the object you want to control access to.

Examples:

* VM instances
* Storage buckets
* Databases
* Kubernetes clusters

IAM permissions can be applied at different levels:

```text
Organization
     ↓
Folder
     ↓
Project
     ↓
Resource
```

Permissions **inherit downward**.

---

# 🏢 Real-Life Example

Imagine a **company using GCP**.

```text
Company: ABC Technologies
```

### Employees

👨‍💻 DevOps Engineer
📊 Finance Manager
👨‍💻 Developer

---

### IAM Access Example

| User            | Role           | Resource           |
| --------------- | -------------- | ------------------ |
| DevOps Engineer | Compute Admin  | VM Instances       |
| Developer       | Viewer         | Kubernetes Cluster |
| Finance Manager | Billing Viewer | Billing Account    |

---

### Example Policy

```text
Member: devops@company.com
Role: Compute Admin
Resource: Project
```

Meaning:

The **DevOps engineer can manage virtual machines in the project**.

---

# 📊 Example IAM Policy Structure

```text
Resource: Project
│
├── Member: devops@company.com
│      Role: Compute Admin
│
├── Member: developer@company.com
│      Role: Viewer
│
└── Member: finance@company.com
       Role: Billing Viewer
```

---

# 🎯 Why IAM is Important

IAM provides:

* 🔐 Strong security
* 👥 Controlled access
* 📊 Better resource management
* 🏢 Enterprise governance
* ⚙️ Fine-grained permissions

---

# 🧠 Simple Way to Remember

| Concept  | Simple Meaning  |
| -------- | --------------- |
| Member   | Who             |
| Role     | What permission |
| Resource | Where           |

Example:

```text
Praveen (Member)
       ↓
Compute Admin (Role)
       ↓
VM Instance (Resource)
```

---

# ✅ Summary

IAM is used to **control access to Google Cloud resources**.

IAM structure:

```text
Member + Role + Resource = Access Control
```

Using IAM properly helps organizations maintain **security, control, and compliance in cloud environments**.

---

If you want, I can also help you create **Day-04 README: GCP Global Infrastructure (Regions, Zones, and Data Centers)** with **nice diagrams and emojis**, which will make your **GitHub repository look very professional for DevOps portfolios. 🚀**
