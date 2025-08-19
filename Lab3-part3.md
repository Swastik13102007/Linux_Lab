In **Linux**, **users** and **groups** are central concepts for managing access to files and system resources. Here’s a breakdown of the **types of users** and **groups** you can create, as well as their basic roles.

---

## ✅ **1. Users in Linux**

A **user** in Linux represents an individual account, and each user can be assigned specific **permissions** to access files, execute programs, and interact with the system.

### Types of Users:

1. **Root User (Superuser)**

   * **Username**: `root`
   * **ID**: `UID 0` (The user ID for `root` is always 0)
   * **Role**: The most powerful user on the system. Has **full control** over the system, can modify anything, and execute any command.
   * **Privileges**: Can access, modify, and delete any file, even system files.

2. **Normal User**

   * Regular users who have access only to their files and certain system files.
   * **ID**: Assigned a unique `UID` starting from `1000` (typically, depending on your Linux distribution).
   * **Role**: Can execute commands, edit files, and access files in their home directories.
   * **Privileges**: They are restricted by permissions (e.g., they can’t access or modify files owned by the root user unless granted explicit permission).

3. **System User**

   * **UID**: Typically lower than `1000`.
   * **Role**: Used by system services and processes. These users don't log in directly, but are associated with daemons or background services like **www-data** (for web servers) or **mysql** (for the MySQL service).
   * **Privileges**: Limited access for service operation purposes.

![Image](./users.png)
   ---

   ## ✅ **2. Groups in Linux**

A **group** in Linux is a collection of users. By organizing users into groups, you can control access to files or directories that are shared among users of the same group. This makes managing permissions much easier.

### Types of Groups:

1. **Primary Group**
   Every user is assigned a **primary group** when created. This is the group that the user belongs to by default.

   * **Example**: If you create a user `alice`, the primary group might be `alice` as well, which is created automatically during user creation.

2. **Secondary Groups**
   A user can belong to **multiple groups**. Secondary groups provide a way to grant additional access to specific resources.

   * For example, the user `alice` might also be part of the group `developers`, giving her additional access to certain files.

3. **System Group**
 Similar to system users, system groups are used for special purposes (e.g., service groups like `www-data`, `mysql`, etc.).

   * These groups often don’t have interactive logins and are associated with system processes.

   ---

   ## ✅ **3. Creating and Managing Users & Groups**

### **Create a New User**

Use the `adduser` command to create a new user and assign it a home directory.

