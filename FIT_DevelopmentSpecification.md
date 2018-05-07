## FIT Development Specification 
This is the suggested way for building a web/app project in FIT or Chears. Developers should be able to handle the following techniques. 

## Basic 
**1. Frontend:**
- Web: 
	- JavaScript framework: [vue.js](https://github.com/vuejs/vue) , use [vue-cli](https://github.com/vuejs/vue-cli) for project scaffolding
	- CSS framework: [Bootstrap3](http://getbootstrap.com/docs/3.3/) or [Bootstrap4](https://getbootstrap.com/)
- iOS: **Objective-C** or **Swift** + **Xcode**
- Android: **Java** + **Android Studio** (Not consider kotlin at this moment)

**2. Backend:**
- Server Side Language: **PHP** framework [Codeigniter](https://codeigniter.com/) or [Laravel](https://laravel.com/), depends on project scale and requirements.
- Database: **MySQL** , [Redis](https://redis.io/)

## Advanced 
**1. API Design:**
- Use **RESTful** API. **POST/GET/PUT/DELETE** for **CRUD**(Create/Retrieve/Update/Delete) data, use **POST** for other web services. 
		example: 
			(請Vincent補充多幾個example)
- API responses in JSON format, contains the following fields: 
	- status: Status Code, listed below:
		>200 – Success
		401 – Unauthorized
		403 – Permission Denied
		405 – Wrong API Method
		422 – Invalid input / Result not found
		400 – Other errors
	- message: Error Message or "OK" 
	- data: Requested Data
- Use [Postman](https://www.getpostman.com/) for API testing

**2. Version Control** 
- Use [Bitbucket](https://bitbucket.org/) for repository hosting. Need to familiar with **Git**.
- Follow the workflow of [Git Flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) for merging and releasing codes (One master branch, one dev branch and each developer has his own branch. Merge developers’ branches to dev branch for development, merge dev branch to master branch for release). 

**3. Server** 
(請server同事補充下，有D咩techniques系新同事需要識的)
- **AWS** for non-mainland projects
- **Aliyun** for mainland projects

## Rules	
**1. Frontend and Backend separation:**
Frontend and Backend projects should be separated completely from each other. All applications should be communicated via API.

**2. User authentication:**
Use token based authentication, **DO NOT USE session**. 

**3. Multiple Language System:**
For each API, check user preferred language in backend and only response the message in that language.
Language Code: 
>en – English
	zh – 繁體中文
	cn – 简体中文

**4. Multiple Role System:**
For each API, check user permission in backend. In Frontend, simply make the components invisible or disable if user does not have the permission. 

**5. Database**
In general cases, **DO NOT USE** view, stored procedure, function and foreign key. Logic should be handled in PHP level. Can use event for scheduled task. 

**6. Naming Convention:**
Use **camelCase** for variables in javascript, API, PHP and MySQL (except MySQL table name use lower case under_score).

**7. Multiple Site**
For website development, there should be at least 2 sites: one Development Site and one Production Site (Sometimes also need one more UAT Site). These sites should share the same PHP codes, but link to different databases. Never mix data from different database.