node('workers') {
	try {
		stage('Checkout') {
			echo "Checkout source code from scm"
			checkout scm
		}
	} catch(err) {
		echo "Handling errors"
	} finally {
		echo "Cleaning up"
	}
}

