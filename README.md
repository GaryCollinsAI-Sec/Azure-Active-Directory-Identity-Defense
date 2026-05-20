# Identity & Access Security Lab (Microsoft Entra ID / Azure)
**Enterprise Identity Management: RBAC, MFA, and Least Privilege Enforcement**

<hr />

## 📖 Project Overview
This lab demonstrates the end-to-end configuration of **Microsoft Entra ID (formerly Azure Active Directory)**. The primary objective was to secure a cloud tenant by implementing granular **Role-Based Access Control (RBAC)** and enforcing the **Principle of Least Privilege (PoLP)**. Through this implementation, I successfully restricted administrative capabilities, ensured account security via MFA, and validated security boundaries through intentional "Access Denied" testing.

## 🚀 Key Features Implemented
*   **Hierarchical User Provisioning:** Scalable creation of administrative (Manager) and restricted (Intern) accounts.
*   **Security Defaults & MFA:** Hardening the tenant against credential-based attacks using Multi-Factor Authentication.
*   **Zero-Trust Password Policies:** Implementing mandatory password rotations upon first login to ensure account ownership.
*   **RBAC Validation:** Documenting the physical limitations of restricted roles to prove security compliance.

<hr />

## 🛠️ Configuration & Execution

### 1. Identity & Group Architecture
I established a structured directory by provisioning users with job-specific functions and organizing them into security groups for streamlined permission management.
*   **Global Admin:** Full tenant authority for core configuration.
*   **Manager:** Assigned *User Administrator*—authorized for people management but restricted from security escalation.
*   **Intern:** Assigned *Reader*—read-only access to verify resources without modification power.

<img src="https://github.com/user-attachments/assets/5d7318a8-51f8-4e56-a4f1-4be41af24b3d" width="90%" />

**Figure 1:** Provisioning the Student Intern and Manager accounts within the directory.

<img src="https://github.com/user-attachments/assets/9e5d561e-c74f-4888-a9e9-8ab12c5a0838" width="90%" />

**Figure 2:** Creating Security Groups to apply standardized RBAC policies across multiple users.

<hr />

### 2. Zero-Trust Authentication & MFA
To align with modern security standards, I enforced **Security Defaults**. This requires all users to register for Multi-Factor Authentication and update temporary credentials immediately upon their first session.

<img src="https://github.com/user-attachments/assets/80488667-2762-4323-82a9-d43af953b3de" width="90%" />

**Figure 3:** Initial login as the Manager account, triggering the Zero-Trust password update requirement.

<img src="https://github.com/user-attachments/assets/bc3eb311-c6ee-4b4b-81ba-50196254b54e" width="60%" />

**Figure 4:** Successful enforcement of Multi-Factor Authentication (MFA) via the Microsoft Authenticator app.

<hr />

### 3. Proving Least Privilege (The "Audit" Test)
The core of this lab was proving that security boundaries actually work. In this test, I logged in as the **Manager**. While the Manager can reset passwords, they are **blocked** from assigning new roles to users, preventing unauthorized "privilege escalation."

<img src="https://github.com/user-attachments/assets/e42d273c-4ca8-4463-9f48-5b15ee2bbd2e" width="90%" />

**🔴 Evidence of Security Boundary:** In the screenshot, the *"Add assignments"* button is disabled. This confirms that the Manager account operates under Least Privilege and cannot grant themselves or others additional administrative power.

<hr />

## 🛡️ Security Posture Summary
| Threat Vector | Mitigation Strategy | Result |
| :--- | :--- | :--- |
| **Credential Theft** | MFA Security Defaults | 99.9% reduction in account compromise. |
| **Privilege Escalation** | RBAC Scoping | Managers cannot grant Global Admin rights. |
| **Unauthorized Modification** | Reader Roles | Interns can audit without risk of deletion. |

<hr />



<h2>🔗 Project Links</h2>
<p>
  <a href="https://github.com/GaryCollinsAI-Sec">Main Portfolio</a>
</p>

