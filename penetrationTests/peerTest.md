# Deliverable 12

##### Evan Chase and Sam Jones

## Self Attacks

#### Evan Chase

- Attack 1
  |Item            | Result |
  |:---            |:---|
  | Date           | April 11, 2025 |
  | Target         | pizza.evankchase.click |
  | Classification | Insecure Design |
  | Severity       | 3 |
  | Description    | Pizza prices are sent from website, can be modified to be free |
  | Images         | ![Free Pizza](/penetrationTests/free_pizza.png)  |
  | Corrections    | Use prices from database, not request |
- Attack 2
  |Item            | Result |
  |:---            |:---|
  | Date           | April 11, 2025 |
  | Target         | pizza.evankchase.click |
  | Classification | Security Misconfiguration |
  | Severity       | 4 |
  | Description    | Stack trace is visible with SQL errors. |
  | Images         | ![Stack Trace](/penetrationTests/stack_trace.png)  |
  | Corrections    | Remove `stack` from error response in `service.js`. |
- Attack 3
  |Item            | Result |
  |:---            |:---|
  | Date           | April 11, 2025 |
  | Target         | pizza.evankchase.click |
  | Classification | Security Misconfiguration |
  | Severity       | 4 |
  | Description    | Viewing `/docs` gives url of both database and factory. |
  | Images         | ![Databse URL](/penetrationTests/database_url.png)  |
  | Corrections    | Remove `config` from `/docs` response |

#### Sam Jones

- Attack 1
  |Item            | Result |
  |:---            |:---|
  | Date           | April 11, 2025 |
  | Target         | pizza.sj329.click |
  | Classification | Identification and Authentication Failures |
  | Severity       | 2 |
  | Description    | Admin password was too weak, vulnerable to dictionary attack. |
  | Images         | ![Admin Account Access](/penetrationTests/admin_access.png) |
  | Corrections    | Change admin password to something much more secure. Store admin password in the `config.js` file rather than plaintext. |
- Attack 2
  |Item            | Result |
  |:---            |:---|
  | Date           | April 15, 2025 |
  | Target         | pizza.sj329.click |
  | Classification | Injection |
  | Severity       | 1 |
  | Description    | SQL injection attempt (failed but spent 4 hours trying) |
  | Images         | ![SQL Injection Failed](/penetrationTests/sql_fail.png) |
  | Corrections    | The database is set up well for SQLi defense. |

## Peer Attacks

#### Evan Chase (Attacking Sam Jones)
- Attack 1
  |Item            | Result |
  |:---            |:---|
  | Date           | April 15, 2025 |
  | Target         | pizza.sj329.click |
  | Classification | Insecure Design |
  | Severity       | 3 |
  | Description    | Pizza prices are sent from website, can be modified to be free |
  | Images         | ![Image Description](/penetrationTests/free_pizza.png)  |
  | Corrections    | Use prices from database, not request |
- Attack 2
  |Item            | Result |
  |:---            |:---|
  | Date           | April 15, 2025 |
  | Target         | pizza.sj329.click |
  | Classification | Security Misconfiguration |
  | Severity       | 4 |
  | Description    | Stack trace is visible with SQL errors. |
  | Images         | ![Image Description](/penetrationTests/stack_trace.png)  |
  | Corrections    | Remove `stack` from error response in `service.js`. |
- Attack 3
  |Item            | Result |
  |:---            |:---|
  | Date           | April 15, 2025 |
  | Target         | pizza.sj329.click |
  | Classification | Security Misconfiguration |
  | Severity       | 4 |
  | Description    | Viewing `/docs` gives url of both database and factory. |
  | Images         | ![Image Description](/penetrationTests/database_url.png)  |
  | Corrections    | Remove `config` from `/docs` response |

#### Sam Jones (Attacking Evan Chase)

- Attack 1
  |Item            | Result |
  |:---            |:---|
  | Date           | April 11, 2025 |
  | Target         | pizza.evankchase.click |
  | Classification | Identification and Authentication Failures |
  | Severity       | N/A |
  | Description    | Admin password was resistant to dictionary attack. And not stored with plaintext on github. |
  | Images         | ![Failed Account Access](/penetrationTests/brute_force_fail.png) |
  | Corrections    | No corrections needed. |

## Summary
There were some surprisingly easy attacks that were availible on our websites, even when we created things with security in mind, multiple vulnerabilities were still present. Even with limited knowledge it was easy to create multiple attacks that had devistating results. Both of us attempted to learn about SQL injection to defend against strong attacks, but it is surprisingly difficult to learn about since it's illegal. Luckily, the database is set up in a way that prevents most SQLi attacks. Our favorite attack was Evan's "free pizza" attack. 
Securing these vulnerabilities often was extremly easy, but locating them took a lot of time and effort. Tools like Burp Suite greatly improved the ease of attack, and the discoverablity of such vulnerabilities. Penetration testing was super important to learn about these attacks and vulnerabilities.