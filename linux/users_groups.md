# User & Group Management

## Users

### Create Users
| **Command** | **Description** |
|---|---|
| `useradd username`                    | Create a new user with defaults.  |
| `useradd -u 1500 username`            | Create user with specific UID.    |
| `useradd -g primarygroup username`    | Set primary group.                |
| `useradd -G grp1,grp2 username`       | Add user to supplementary groups. |
| `useradd -c "Full Name" username`     | Set GECOS/comment field.          |

### Customize User Defaults
| **Command** | **Description** |
|---|---|
| `useradd -D` | View or modify default settings. |

### Additional Options
| **Command** | **Description** |
|---|---|
| `useradd -b /base/dir username`       | Set base directory for home.            |
| `useradd -f days username`            | Set INACTIVE days after password expiry.|
| `useradd -e YYYY-MM-DD username`      | Set account expiration date.            |
| `useradd -s /bin/bash username`       | Set login shell.                        |
| `useradd -k /path/to/skel username`   | Use alternate skeleton directory.       |

### Password Management
| **Command** | **Description** |
|---|---|
| `passwd username` | Set or change user password. |

## Groups

### Create Groups
| **Command** | **Description** |
|---|---|
| `groupadd newgroup` | Create a new group with default GID. |
| `groupadd -g 1007 newgroup` | Create group with a specific GID. |
| `groupadd -r sysgroup` | Create a system group (low GID). |

### View Groups
| **Command** | **Description** |
|---|---|
| `grep groupname /etc/group`   | Show group entry from local files. |
| `getent group groupname`      | Show group entry. |

### Modify Groups
| **Command** | **Description** |
|---|---|
| `groupmod -n newname oldname` | Rename a group. |
| `groupmod -g 2000 groupname`  | Change group GID. |

### Delete Groups
| **Command** | **Description** |
|---|---|
| `groupdel groupname`  | Delete a group.                              |
| `find / -nogroup`     | Find files belonging to non‑existent groups. |