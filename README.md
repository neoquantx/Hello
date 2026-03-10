pipeline
{
        agent any
        stages
        {
            stage("Checkout")
            {
                steps
                {
                    git branch: "master", url:"https://github.com/neoquantx/Hello.git"
                }
            }
            stage("Build")
            {
                steps
                {
                    sh "mvn clean package"
                }
            }
            stage("Test")
            {
                steps
                {
                    sh "mvn test"
                }
            }
        }
}
