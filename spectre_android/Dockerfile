
FROM ubuntu:20.04


RUN apt-get update && \
    apt-get install -y \
    git \
    openjdk-11-jdk \
    wget \
    unzip


RUN git clone https://gitlab.com/spectre.app/android.git /opt/spectre-android


WORKDIR /opt/spectre-android


RUN wget https://dl.google.com/android/repository/commandlinetools-linux-7302050_latest.zip -O /tmp/sdk.zip && \
    unzip /tmp/sdk.zip -d /opt/android-sdk && \
    rm /tmp/sdk.zip


ENV PATH="/opt/android-sdk/tools/bin:${PATH}"


RUN yes | sdkmanager --licenses


RUN sdkmanager "build-tools;30.0.3" "platforms;android-30"


RUN ./gradlew assembleRelease




CMD ["./gradlew", "installRelease"]
