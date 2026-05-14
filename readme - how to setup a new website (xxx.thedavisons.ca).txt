Instructions on how to setup new website (March 2026)

Webnames.ca is the company that holds the registration for the domains www.thedavisons.ca and www.hbhomes.ca
Cloudflare.com is the website that manages the DNS
Amazon hosts a static website for both the davisons.ca and hbhomes.ca

1. When you add a new site you need to add it to cloudflare (adding a new CNAME). 
   No longer using Route 53 in Amazon as cloudflare helps me with SSL certs for free
2. Then you need to create a new bucket in S3 first as the endpoint will have to go 
    into the CNAME properties
3. I use VS code to build the websites 
4. I use GitHub to manage the code. You can push changes using VS Code to GitHub
5. I have setup a workflow in GitHub to manage the workflow for all the websites. 
   The workflow will push any changes from GitHub to Amazon S3
6. Using the app call cloudberry is not necessary 


|   
+---.github
|   \---workflows
|           deploy.yml
|           
|       
\---sites
    +---hbhomes.ca
    |   \---root
    |       |   .gitignore
    |       |   index.html
    |       |   sitemap.xml
    |       |   
    |       |       
    |       +---muskoka-mini-excavation
    |       |       index.html
    |       |       
    |       \---services
    |               index.html
    |               
    \---thedavisons.ca
        +---257
        |   |   contactUs.html
        |   |   floorplan.html
        |   |       
        |   \---Templates
        |           Templates.dwt
        |           
        +---99miller
        |   |   createJSONphotoManifest.py
        |   |   index.html
        |   |   miller_data.json
        |   |   rename.py
        |   |   startWebServerForTesting.bat
        |   |   
        |   |           
        |   +---images
        |   |   +---basement
        |   |   |       basement_010.jpg
        |   |   |       
        |   |   +---common
        |   |   |       common_008.jpg
        |   |   |       
        |   |   \---main_floor
        |   |           mainfloor_010.jpg
        |   |           mainfloor_020.jpg
        |   |           
        |   \---utilities
        |       +---electricity
        |       |       2024-02-16.pdf
        |       |       
        |       \---gas
        |               2024-02-22.pdf

