# Learning notes

## JWT Pizza code study and debugging

As part of `Deliverable ⓵ Development deployment: JWT Pizza`, start up the application and debug through the code until you understand how it works. During the learning process fill out the following required pieces of information in order to demonstrate that you have successfully completed the deliverable.

| User activity                                       | Frontend component     | Backend endpoints                                     | Database SQL |
| --------------------------------------------------- | ---------------------- | ----------------------------------------------------- | ------------ |
| View home page                                      | home.tsx               | none                                                  | none         |
| Register new user<br/>(t@jwt.com, pw: test)         | register.tsx           | [POST]/api/auth                                       |              |
| Login new user<br/>(t@jwt.com, pw: test)            | login.tsx              | [PUT]/api/auth                                        |              |
| Order pizza                                         | menu.tsx payment.tsx   | [GET]/api/order/menu [GET]/api/order [POST]/api/order |              |
| Verify pizza                                        | delivery.tsx           | [POST]/api/order/verify                               |              |
| View profile page                                   | dinerDashboard.tsx     | [GET]/api/order                                       |              |
| View franchise<br/>(as diner)                       | franchiseDashboard.tsx |                                                       |              |
| Logout                                              | logout.tsx             | [DELETE]/api/auth                                     |              |
| View About page                                     | about.tsx              |                                                       |              |
| View History page                                   | history.tsx            |                                                       |              |
| Login as franchisee<br/>(f@jwt.com, pw: franchisee) | login.tsx              |                                                       |              |
| View franchise<br/>(as franchisee)                  | franchiseDashboard.tsx |                                                       |              |
| Create a store                                      | createStore.tsx        |                                                       |              |
| Close a store                                       | closeStore.tsx         |                                                       |              |
| Login as admin<br/>(a@jwt.com, pw: admin)           | login.tsx              |                                                       |              |
| View Admin page                                     | adminDashboard.tsx     |                                                       |              |
| Create a franchise for t@jwt.com                    | createFranchise.tsx    |                                                       |              |
| Close the franchise for t@jwt.com                   | closeFranchise.tsx     |                                                       |              |
