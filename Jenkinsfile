if  (env.BRANCH_NAME != 'master') {
        checkout()
        build()
        test()
        uat()

        // test whether this is a regular branch build or a merged PR build
        if (!isPRMergeBuild()) {
            test()
        } else {
            // Pull request
            uat()
        }
    } // master branch / production
    else { 
        uat()
        )
    }
}

def isPRMergeBuild() {
    return (env.BRANCH_NAME ==~ /^PR-\d+$/)


    def checkout () {
    stage 'Checkout code'
    context="continuous-integration/jenkins/"
    context += isPRMergeBuild()?"pr-merge/checkout":"branch/checkout"
    checkout scm
    setBuildStatus ("${context}", 'Checking out completed', 'SUCCESS')
}

def build() {
    stage 'Build'
    println 'This happens only on master'
}
def test() {
    stage 'Testing'
    println 'This happens only on Testing env'
}

def uat() {
    stage 'Build'
    println 'This happens only on UAT'
}
