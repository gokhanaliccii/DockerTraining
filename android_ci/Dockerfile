FROM openjdk:8 

ENV ANDROID_HOME /android_sdk
ENV SDK_LINK https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
ENV SDK_MANAGER ${ANDROID_HOME}/tools/bin/sdkmanager

ENV SDK_VERSION android-26
ENV BUILD_TOOLS 27.0.3

RUN mkdir ${ANDROID_HOME}
  
RUN cd ${ANDROID_HOME} && wget -O sdk.zip ${SDK_LINK} && unzip sdk.zip 
RUN rm ${ANDROID_HOME}/sdk.zip

RUN mkdir ~/.android && touch ~/.android/repositories.cfg

RUN yes | ${SDK_MANAGER} --licenses 
RUN ${SDK_MANAGER} --update
RUN ${SDK_MANAGER} "platform-tools" "extras;android;m2repository" "android-${BUILD_TOOLS}" "platforms;${SDK_VERSION}" 
RUN yes | ${SDK_MANAGER} --licenses
RUN ${SDK_MANAGER} --update
