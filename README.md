# AI Automation Internship — Day 03

Today I learned the fundamentals of APIs, REST, and HTTP by building and testing a lead-management automation. I connected n8n webhooks with Google Sheets and used Postman to test the complete CRUD workflow. I also practiced Git and GitHub by forking and contributing to an open-source project.

## What I Learned

### APIs and REST APIs
An API (Application Programming Interface) allows different software systems to communicate. A REST API commonly uses HTTP requests, resource-based endpoints, and JSON data to exchange information between a client and a server.

The basic communication flow is:

Client → HTTP request → Server
Client ← HTTP response ← Server

### HTTP Methods and CRUD
I learned how common HTTP methods map to CRUD operations:

| HTTP method | CRUD operation | Purpose |
|---|---|---|
| POST | Create | Add a new resource |
| GET | Read | Retrieve an existing resource |
| PUT | Update | Modify an existing resource |
| DELETE | Delete | Remove an existing resource |

### HTTP Status Codes
I also studied the status codes returned by servers to describe the result of a request:

| Status code | Meaning |
|---|---|
| 200 OK | The request completed successfully |
| 201 Created | A new resource was created |
| 400 Bad Request | The request was invalid or malformed |
| 401 Unauthorized | Authentication is required or invalid |
| 404 Not Found | The requested resource was not found |
| 500 Internal Server Error | An unexpected server error occurred |

### Headers and Authentication
I also learned about common request headers and authentication methods:
- **Content-Type** — specifies the format of the data being sent (e.g. `application/json`)
- **Authorization** — carries credentials needed to access a resource
- **Accept** — specifies the format the client expects in the response
- **API Keys** — a unique string used to identify and authorize a client
- **Bearer Tokens** — a token sent in the Authorization header to prove a request is authenticated

### JSON Data
I used JSON to send lead information between Postman and n8n. The workflow handles fields such as name, email, phone, company, and interest, while Google Sheets also records the creation date.

## Lead-Management Automation

I created an active n8n workflow with four webhook-based operations, all combined into a single workflow. Each webhook receives a request, performs the corresponding Google Sheets action, and returns a response.

| Operation | HTTP method | Relative endpoint | Google Sheets action |
|---|---|---|---|
| Create lead | POST | `/create-lead` | Append a row |
| Get all leads | GET | `/get-leads` | Read all rows |
| Update lead | PUT | `/update-lead` | Find row by email, update it |
| Delete lead | DELETE | `/delete-lead` | Find row by email, delete it |

The complete workflow uses this flow:

Postman → n8n webhook → Google Sheets operation → Webhook response

I configured a Postman environment with a reusable `baseURL` variable and created a collection — **MATalogics Lead Management API** — with separate requests for all four operations, using collection variables, JSON request bodies, and a `Content-Type: application/json` header on each request.

## Google Sheet Structure

Sheet name: **Lead Management**
Columns: `Name`, `Email`, `Phone`, `Company`, `Interest`, `Created At`

## Git and GitHub Practice

I practiced core Git commands (`init`, `clone`, `add`, `commit`, `push`, `pull`) and contributed to an open-source project: **awesome-n8n-templates**, a curated collection of reusable n8n workflow templates. I forked the repository, improved the descriptions of five templates in the OpenAI_and_LLMs section, and submitted [Pull Request #177](https://github.com/enescingoz/awesome-n8n-templates/pull/177).

- Original repository: https://github.com/enescingoz/awesome-n8n-templates
- My fork: https://github.com/Samra-Ishaq/awesome-n8n-templates

## Day 03 Artifacts

- Day 03 internship report — `Day-03/Report/Day-03 Report.docx`
- n8n lead-management workflow — `Day-03/n8n/Lead Management Workflow.json`
- Postman collection — `Day-03/Postman/MATalogics Lead Management API.postman_collection.json`
- Postman environment — `Day-03/Postman/Environment.postman_environment.json`
- Google Sheet reference — `Day-03/Google Sheets/Google Sheet Link.txt`
- Postman screenshots — `Day-03/Postman/Screenshots/`
- n8n workflow screenshot — `Day-03/n8n/Workflow Screenshot.png`
- GitHub learning artifacts — `Day-03/GitHub/`

## Key Takeaway

Today's work helped me understand how a client sends HTTP requests, how an automation workflow processes those requests end-to-end, and how to store and manage real data through a no-code backend — connecting API theory directly to a working, testable system.
