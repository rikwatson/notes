# Using Docker for Android Testing
Look, a DOCKERFILE
 
```
FROM java:8
ENV DEBIAN_FRONTEND noninteractive
# Dependencies
RUN dpkg --add-architecture i386 && apt-get update && apt-get install -yq libsdl1.2debian:i386 zlib1g:i386 libncurses5:i386 ant maven --no-install-recommends
ENV GRADLE_URL http://services.gradle.org/distributions/gradle-2.2.1-all.zip
RUN curl -L ${GRADLE_URL} -o /tmp/gradle-2.2.1-all.zip && unzip /tmp/gradle-2.2.1-all.zip -d /usr/local && rm /tmp/gradle-2.2.1-all.zip
ENV GRADLE_HOME /usr/local/gradle-2.2.1
# Download and untar SDK
ENV ANDROID_SDK_URL http://dl.google.com/android/android-sdk_r24.1.2-linux.tgz
RUN curl -L "${ANDROID_SDK_URL}" | tar --no-same-owner -xz -C /usr/local
ENV ANDROID_HOME /usr/local/android-sdk-linux
ENV ANDROID_SDK /usr/local/android-sdk-linux
ENV PATH ${ANDROID_HOME}/tools:$ANDROID_HOME/platform-tools:$PATH
# Install Android SDK components
ENV ANDROID_SDK_COMPONENTS tools,platform-tools,android-22,build-tools-22.0.1,sys-img-armeabi-v7a-android-22,extra-android-m2repository,extra-google-m2repository
RUN echo y | android update sdk --no-ui --all --filter "${ANDROID_SDK_COMPONENTS}" --force
# Create emulator
RUN echo "no" | android create avd \
                --force \
                --name test \
                --target android-22 \
                --abi armeabi-v7a \
                --skin WVGA800 \
                --sdcard 512M
CMD emulator -avd test -force-32bit
# Support Gradle
ENV TERM dumb
ENV JAVA_OPTS -Xms256m -Xmx512m
```

 
# To Investigate

 * [AWS Device farm](./aws_device_farm)