# Learning notes

## JWT Pizza code study and debugging

As part of `Deliverable ⓵ Development deployment: JWT Pizza`, start up the application and debug through the code until you understand how it works. During the learning process fill out the following required pieces of information in order to demonstrate that you have successfully completed the deliverable.

| User activity                                       | Frontend component     | Backend endpoints                                     | Database SQL                                        |
| --------------------------------------------------- | ---------------------- | ----------------------------------------------------- | --------------------------------------------------- |
| View home page                                      | home.tsx               | none                                                  | none                                                |
| Register new user<br/>(t@jwt.com, pw: test)         | register.tsx           | [POST]/api/auth                                       |                                                     |
| Login new user<br/>(t@jwt.com, pw: test)            | login.tsx              | [PUT]/api/auth                                        |                                                     |
| Order pizza                                         | menu.tsx payment.tsx   | [GET]/api/order/menu [GET]/api/order [POST]/api/order |                                                     |
| Verify pizza                                        | delivery.tsx           | [POST]/api/order/verify                               |                                                     |
| View profile page                                   | dinerDashboard.tsx     | [GET]/api/order                                       |                                                     |
| View franchise<br/>(as diner)                       | franchiseDashboard.tsx | [GET]/api/order                                       |                                                     |
| Logout                                              | logout.tsx             | [DELETE]/api/auth                                     | DELETE FROM auth WHERE token=?                      |
| View About page                                     | about.tsx              | none                                                  |                                                     |
| View History page                                   | history.tsx            | none                                                  |                                                     |
| Login as franchisee<br/>(f@jwt.com, pw: franchisee) | login.tsx              | [PUT]/api/auth                                        | /api/franchise                                      |
| View franchise<br/>(as franchisee)                  | franchiseDashboard.tsx | /api/franchise                                        |                                                     |
| Create a store                                      | createStore.tsx        |                                                       | INSERT INTO store (franchiseId, name) VALUES (?, ?) |
| Close a store                                       | closeStore.tsx         |                                                       |                                                     |
| Login as admin<br/>(a@jwt.com, pw: admin)           | login.tsx              | /api/auth                                             |                                                     |
| View Admin page                                     | adminDashboard.tsx     | /api/auth                                             |                                                     |
| Create a franchise for t@jwt.com                    | createFranchise.tsx    | /api/franchise/                                       |                                                     |
| Close the franchise for t@jwt.com                   | closeFranchise.tsx     | /api/franchise/                                       |                                                     |
