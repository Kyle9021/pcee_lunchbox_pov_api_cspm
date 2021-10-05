# pcee_lunchbox_pov_api_cspm
Creates the report needed to pull high level KPIs from the Prisma Cloud Enterprise Edition Console

# Last confirmed working 10.05.2021
[![CodeFactor](https://www.codefactor.io/repository/github/kyle9021/pcee_lunchbox_pov_api_cspm/badge)](https://www.codefactor.io/repository/github/kyle9021/pcee_lunchbox_pov_api_cspm)

# Assumptions

* You're using PRISMA CLOUD ENTERPRISE EDTION
* You're using an OS that supports Bash, such as Linux or Mac OS to run this from
* You understand how to harden this script for production environments

  * The biggest suggestion here is to not save the script with your secret key and access key in it. A better way to do this might be to have a seperate script which exports those credentials as environment variables. My goal with this script is to simplify the process for those who are learning to work with the Prisma Cloud Enterprise Edition API. 

* To simplify, we've provided the instructions to export the secret and access key as env variables. 
  
* If you decide to keep the keys in this script, then it's critical you:
  
   * Add it to your `.gitignore` (if using git) file and `chmod 700 lunchbox_report.sh` between steps 3 and 4 so that others can't read, write, or excute it. 

# Instructions

Step 1:  Install jq: https://stedolan.github.io/jq/download/:

         * debian/ubuntu `sudo apt-get install jq`
         * macOS `sudo brew install jq`
         * RHEL `sudo yum install jq`
         
Step 2:  `git clone https://github.com/Kyle9021/pcee_lunchbox_pov_api_cspm`  
Step 3:  `cd pcee_lunchbox_pov_api_cspm/`  
Step 4:  Export the following variables directly in your terminal/shell by replacing the values between the `"<>"` with the correct data from your console. Enter the below commands in your shell prior to running the script.    
```
export API_URL="<CONSOLE_API_URL>"
export ACCESS_KEY="<ACCESS_KEY>"
export SECRET_KEY="<SECRET_KEY>"
```
Step 5:  `bash lunchbox_report.sh`  
Step 6:  `ls` to see your report or go through the GUI to access the directory and open in excel/sheets.  

# Links to reference

* [Official JQ Documentation](https://stedolan.github.io/jq/manual/)
* [Exporting variables for API Calls and why I choose bash](https://apiacademy.co/2019/10/devops-rest-api-execution-through-bash-shell-scripting/)
* [PAN development site](https://prisma.pan.dev/)
