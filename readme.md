# README Outline:
* Project Description
* Prerequisites
* Usage
	* Building
	* Testing
	* Deployment
* Additional Notes
* Version History and Retention
* License
* Contributions
* Contact Information
	* Citing this code
* Acknowledgements

# Project Description
This repository contains the source code for the United States Department of Transportation (U.S. DOT)  Intelligent Transportation Systems Joint Program Office (ITS JPO) CodeHub website located at [https://its.dot.gov/code](https://its.dot.gov/code). ITS CodeHub provides a public, centralized location for ITS JPO source code to promote source code discovery and reuse. This repository can be stood up independently from all other repositories. 


# Prerequisites
## Requires:
- Basic web server
  - This repository requires a basic web server to run and display the list of registered repositories. Currently, we are using [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) from the Visual Studio Code extension library for local development and testing.
- ITS JPO files: 
  - CSS
  - JavaScript
  - Images

The ITS JPO files can be obtained by: 
1. Use a web browser, such as Google Chrome, and navigate to [https://its.dot.gov/code/index.html](https://its.dot.gov/code/index.html)
2. Use the developer tools
3. Go to the "Sources" tab
4.  Open the file directory titled "top"
5.  Open the file directory titled "its.dot.gov"
6.  You will see 4 directories
    1.  code
    2.  css
    3.  images
    4.  js
7. Download the files in the css, images, and js folders.
8. Create 3 directories (css, images, js) at the same level as the "/code" directory found in this repo. Put the downloaded files into their respective directories. 

# Usage
## Building
There is no building required.

## Testing
Most testing is done manually via viewing the site in a web browser. The parts to verify are that the 
- pages all load and display correctly
- downloads function
- URLs to external sites work
- expected number of code repositories display
- Web pages pass 508 Compliance  
The number of repositories is displayed at the top of the [Code Repositories page](https://its.dot.gov/code/code-repositories.html). It should match the number of code repositories found in the json file [repository_list_codehub.json](https://github.com/usdot-jpo-codehub/codehub-standalone/blob/main/code/resources/data/repository_list_codehub.json), as well as the [codehub-standalone_repository-list-generator](codehub-standalone_repository-list-generator) repo in the csv file named "input_repository_list.csv". 

## Deployment
The code can be used to view the web pages by utilizing a web server, such as the one we are currently using, [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) from the Visual Studio Code extension library or by opening the HTML files in a web browser, such as Google Chrome. Note, the code repositories page will not display the list of code repositories without a web server.


# Additional Notes
Due to ITS CodeHub needing to match the style of and live within the ITS JPO website, only parts of the HTML code are intended to be updated in this repo. Within the HTML files, the code is to be updated in 2 places, inclusively:
1. For the left-side page menu:
   - starting at 
		```html 
		<li class="leftNavItem codehub-menu-home"><a href="index.html">ITS CodeHub</a></li>
		```
   - and ending at 
		```html
		<li class="leftNavItem child-menu-item last-menu active"><a href="additional-resources.html">Additional Resources</a></li> 
		```
2. For the page content:
   - starting at 
		```html 
		<main id="pageContent"....>
		```
	-	and ending at 
		```html
		<!--====== END OF MAIN CONTENT =========-->
		```
To update the list of repositories displayed on ITS CodeHub, the [codehub-standalone_repository-list-generator](codehub-standalone_repository-list-generator) repository can be utilized to generate a json file containing the updated list. 


To update the list of repositories displayed on ITS CodeHub, follow the steps below to generate a new version of [repository_list_codehub.json](https://github.com/usdot-jpo-codehub/codehub-standalone/blob/main/code/resources/data/repository_list_codehub.json):
1. Use the scripts and instructions in the [codehub-standalone_repository-list-generator](codehub-standalone_repository-list-generator) repository to generate an updated json file.
2. Rename the file to 
   ```
   repository_list_codehub.json
   ```
3. and copy the updated json file to the 
   ```
   /code/resources/data/
   ```
   location, replacing the existing file.
4. If you wish to change the json file of the main branch of this repository, create a Pull Request with your changes, following our guide at [CONTRIBUTING.md](https://github.com/usdot-jpo-codehub/codehub-standalone/blob/main/code/CONTRIBUTING.MD).

# Version History and Retention
<!-- *A statement of the status of the source code (prototype, alpha, beta, release, etc.), how often users can expect activity on this repository, and a version/release history in the form of a CHANGELOG file. Additionally, include a retention statement that specifies how long this repository will remain publicly accessible*

Example: -->

**Status:** This project is in the release phase.

**Release Frequency:** This project is updated approximately once a month with updated content and additions of new code repositories. 

**Release History:**
See [ITS CodeHub's releases page](https://github.com/usdot-jpo-codehub/codehub-standalone/releases).

**Retention:** This project will remain publicly accessible for a minimum of five years (until at least 07/28/2026).

# License
This project is licensed under the Apache 2.0 License, see [LICENSE](https://github.com/usdot-jpo-codehub/codehub-standalone/blob/master/LICENSE).

# Contributions
Please read [CONTRIBUTING.md](https://github.com/usdot-jpo-codehub/codehub-standalone/blob/main/code/CONTRIBUTING.MD) for details on our Code of Conduct, the process for submitting pull requests to us, and how contributions will be released.

# Contact Information
Contact Name: ITS JPO
Contact Information: data.itsjpo@dot.gov

## Citing this code
When you copy or adapt from this code, please include the original URL you copied the source code from and date of retrieval as a comment in your code.

# Acknowledgements
Thank you to the Department of Transportation for funding the development of this project.