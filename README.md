
# Jenkins
<h2>What is Jenkins?</h2>
<p>Jenkins is an open-source automation server widely used to automate parts of software development, such as building, testing, and deploying applications. It helps developers continuously integrate changes to code and continuously deliver software by automating repetitive tasks.</p>

<h3>Key points about Jenkins:</h3>
<ul>
  <li><strong>Automation:</strong> Jenkins automates tasks like compiling code, running tests, and deploying software, reducing manual effort.</li>
  <li><strong>Continuous Integration / Continuous Delivery (CI/CD):</strong> Jenkins supports CI/CD pipelines, which help teams deliver code changes more frequently and reliably.</li>
  <li><strong>Plugins:</strong> Jenkins has a rich ecosystem of plugins to integrate with many tools and technologies.</li>
  <li><strong>Extensible:</strong> You can customize Jenkins pipelines using a Jenkinsfile, which defines build steps as code.</li>
  <li><strong>Web Interface:</strong> Jenkins provides a web dashboard to monitor builds, configure jobs, and view logs.</li>
  <li><strong>Cross-platform:</strong> Runs on Windows, macOS, Linux, and can be deployed on cloud or local servers.</li>
</ul>

<p>In short, Jenkins helps automate the software lifecycle to improve productivity and software quality.</p>


<!DOCTYPE html>
<html>
<head>
  <title>How Jenkins Runs the Pipeline</title>
</head>
<body>
  <h1>How Jenkins Runs the Pipeline</h1>
  <p>Once triggered (by any of the below methods), Jenkins will:</p>
  <ol>
    <li>Clone your repository.</li>
    <li>Look for the <code>Jenkinsfile</code> in the root directory.</li>
    <li>Execute the pipeline steps defined in the Jenkinsfile:
      <ul>
        <li>Checkout code</li>
        <li>Build (e.g., <code>mvn clean install</code>)</li>
        <li>Run the JAR (<code>java -jar ...</code>)</li>
        <li>Log output to <code>app.log</code> (if specified)</li>
        <li>Deploy, test, etc.</li>
      </ul>
    </li>
  </ol>
</body>
</html>


<!DOCTYPE html>
<html>
<head>
  <title>Jenkins Pipeline Trigger Methods</title>
</head>
<body>
  <h1>Jenkins Pipeline Trigger Methods</h1>

  <h2>1. Manually (Trigger by Yourself)</h2>
  <p>You go to Jenkins and click “Build Now” on your pipeline job.</p>
  <p>This is useful for testing or on-demand builds.</p>

  <h2>2. Automatically (On Git Push / SCM Change)</h2>
  <p>If you've connected your pipeline to GitHub (or any Git SCM), you can set it to auto-trigger when code changes are pushed.</p>
  <p>Jenkins polls Git or uses webhooks (preferred) to start builds.</p>
  
  <h3>How to set it up:</h3>
  <ol>
    <li>Go to your pipeline job &gt; Configure</li>
    <li>Under <strong>Build Triggers</strong>, select “GitHub hook trigger for GITScm polling”.</li>
    <li>In GitHub repo settings, add a webhook to your Jenkins server (usually: <code>http://&lt;jenkins-ip&gt;:8080/github-webhook/</code>).</li>
  </ol>

  <h2>3. Automatically (Scheduled like a Cron job)</h2>
  <p>Jenkins can run pipelines at scheduled times, using a cron-like syntax.</p>
  <p>Example (every day at midnight):</p>
  <pre><code>triggers {
    cron('H 0 * * *') 
}</code></pre>

</body>
</html>

