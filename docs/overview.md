# API Overview

This API is intendended to allow our users to interface with our scanning utilities programatically, giving them the freedom to view, analyse and use the data however they wish. Scans are credited against the account your API key is associated with.

There are a few possible results that our API may return. The exact details of data returned by each route can be found under the indiviual tool routes.

| Status COde                 | Body                      | Typical Cause                                                                                                     |
| --------------------------- | ------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| `200 OK`                    | Results body              | -                                                                                                                 |
| `400 BAD REQUEST`           | Missing name or data      | Your request is malformed.                                                                                        |
| `401 Unauthorized`          | Unauthorized Access       | Your API key is missing, incorrect or expired                                                                     |
| `402 Payment Required`      | Insufficient Credits      | You have insufficient credits on the account associated to the used API key.                                      |
| `404 NOT FOUND`             | Message depends on route. | You requested an unrecognised resource                                                                            |
| `405 METHOD NOT ALLOWED`    | None. Next.js specific.   | You've made a request to a route using a method that has no handler at that route, i.e. used POST at a GET Route. |
| `500 INTERNAL SERVER ERROR` | Situation specific.       | Something has gone wrong on our end. Please contact us.                                                           |

The BEI API supports POST and GET requests. The authentication process differs dependent upon which method is used. You can read about this at <a href="/authentication">Authentication</a>
