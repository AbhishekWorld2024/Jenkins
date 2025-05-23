
# Jenkins

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

