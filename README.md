<img src='https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/Amazon_Web_Services_Logo.svg/768px-Amazon_Web_Services_Logo.svg.png' width=128 height=86></img><br>
<h3>University of San Diego MSADS Final Project - Practical Data Engineering</h3>
<h4><i>Filipp Krasovsky, Fatima Khosravi</i></h4>

This project demonstrates mastery of:
<ul>
  <li>Optimizing SQL Query runtime in an AWS environment</li>
  <li>Deploying a Cloudformation Stack with a scheduled lambda that runs every five minutes</li>
</ul>

<h5><b>Technical Stack:</b></h5>
<ul>
    <li>Python (lambda construction)</li>
    <li>AWS SDK</li>
    <li>SQL</li>
</ul>

<h4><b>Cloudformation Deployment</b></h4>
<h5><b>Summary</b></h5><br>
<p>
    This project deploys a cloudformation stack using a .yaml file and creates a VPC with a private subnet, 
    a redshift cluster attached to the private subnet with a database, and a lambda that executes every five minutes
    through an event bus that inserts a single row into a table in the database. Data is scraped from the random-article url 
    on wikipedia and returns a new title each time.
</p>

<h5><b>Usage and Deployment</b></h5>
<ol type="i">
    <li>Download the module_6_solution.yaml file locally.</li>
    <li>Provided you have an AWS account, go to cloudformation.</li>
    <li>Click "Create Stack" using new resources.</li>
    <li>When prompted, submit the .yaml template.</li>
    <li>(Optional) Modify any of the IPV4 CIDR Blocks, database credentials, or environment variables for stylistic preferences. This template will deploy properly with default values.</li>
</ol>
