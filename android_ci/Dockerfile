FROM openjdk:8 
RUN mkdir android_sdk 
RUN cd android_sdk && wget -O sdk.zip \
&&  https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip \
unzip android.sdk \
&& cd tools/bin \
&& yes | sdkmanager --licenses \
&& sdkmanager "build-tools;25.0.1"  

