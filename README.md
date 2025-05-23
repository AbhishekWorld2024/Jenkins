
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
