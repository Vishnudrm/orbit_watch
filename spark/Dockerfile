FROM apache/spark:3.4.1

USER root

# Install Python dependencies
RUN pip install --no-cache-dir \
    pyspark==3.4.1 \
    delta-spark==2.4.0 \
    sgp4==2.22 \
    skyfield==1.46 \
    requests==2.31.0 \
    kafka-python==2.0.2 \
    pandas==2.0.3

# Download Delta Lake jars into Spark jars directory
RUN curl -o /opt/spark/jars/delta-core_2.12-2.4.0.jar \
    https://repo1.maven.org/maven2/io/delta/delta-core_2.12/2.4.0/delta-core_2.12-2.4.0.jar && \
    curl -o /opt/spark/jars/delta-storage-2.4.0.jar \
    https://repo1.maven.org/maven2/io/delta/delta-storage/2.4.0/delta-storage-2.4.0.jar

USER spark
