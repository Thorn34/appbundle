# appbundle
bundle
git init
git add .
git commit -m "Initial commit with Capacitor Android setup"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/nursing-home-store.git
git push -u origin main
base64 -i /home/ubuntu/nursing-home.keystore
git tag v1.0.0
git push origin v1.0.0
cd /home/ubuntu/nursing-home-store/android
JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64 ./gradlew bundleRelease
/home/ubuntu/nursing-home-store/android/app/build/outputs/bundle/release/app-release.aab
