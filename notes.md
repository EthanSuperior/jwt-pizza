# Learning notes

## JWT Pizza code study and debugging

As part of `Deliverable ⓵ Development deployment: JWT Pizza`, start up the application and debug through the code until you understand how it works. During the learning process fill out the following required pieces of information in order to demonstrate that you have successfully completed the deliverable.

| User activity                                       | Frontend component     | Backend endpoints                                     | Database SQL                                        |
| --------------------------------------------------- | ---------------------- | ----------------------------------------------------- | --------------------------------------------------- |
| View home page                                      | home.tsx               | none                                                  | none                                                |
| Register new user<br/>(t@jwt.com, pw: test)         | register.tsx           | [POST]/api/auth                                       | INSERT INTO auth (token, userId) VALUES (?, ?)      |
| Login new user<br/>(t@jwt.com, pw: test)            | login.tsx              | [PUT]/api/auth                                        | INSERT INTO auth (token, userId) VALUES (?, ?)      |
| Order pizza                                         | menu.tsx payment.tsx   | [GET]/api/order/menu [GET]/api/order [POST]/api/order |                                                     |
| Verify pizza                                        | delivery.tsx           | [POST]/api/order/verify                               |                                                     |
| View profile page                                   | dinerDashboard.tsx     | [GET]/api/order                                       | SELECT id, name FROM user WHERE email=?             |
| View franchise<br/>(as diner)                       | franchiseDashboard.tsx | [GET]/api/order                                       | SELECT id, name FROM store WHERE franchiseId=?      |
| Logout                                              | logout.tsx             | [DELETE]/api/auth                                     | DELETE FROM auth WHERE token=?                      |
| View About page                                     | about.tsx              | none                                                  |                                                     |
| View History page                                   | history.tsx            | none                                                  | none                                                |
| Login as franchisee<br/>(f@jwt.com, pw: franchisee) | login.tsx              | /api/franchise                                        | none                                                |
| View franchise<br/>(as franchisee)                  | franchiseDashboard.tsx | /api/franchise                                        | SELECT id, name FROM store WHERE franchiseId=?      |
| Create a store                                      | createStore.tsx        | /api/franchise/                                       | INSERT INTO store (franchiseId, name) VALUES (?, ?) |
| Close a store                                       | closeStore.tsx         | /api/franchise/                                       | DELETE FROM store WHERE franchiseId=? AND id=?      |
| Login as admin<br/>(a@jwt.com, pw: admin)           | login.tsx              | /api/auth                                             | INSERT INTO auth (token, userId) VALUES (?, ?)      |
| View Admin page                                     | adminDashboard.tsx     | /api/auth                                             | SELECT id, name FROM user WHERE email=?             |
| Create a franchise for t@jwt.com                    | createFranchise.tsx    | /api/franchise/                                       | INSERT INTO franchise (name) VALUES (?)             |
| Close the franchise for t@jwt.com                   | closeFranchise.tsx     | /api/franchise/                                       | DELETE FROM store WHERE franchiseId=?               |
