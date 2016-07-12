
# Java

### Quickstart Archetype

    mvn archetype:generate \
    -DgroupId=com.mycompany.app \
    -DartifactId=my-app \
    -DarchetypeArtifactId=maven-archetype-quickstart \ 
    -DinteractiveMode=false

Be careful, there should be no spaces after the line continuation chacter \.
Note that on Windows, use ^ instead of \.

[Maven in 5 Minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)

### CXF Archetype

    mvn archetype:generate \
    -DgroupId=com.mycompany.srv \
    -DartifactId=my-srv \
    -DarchetypeGroupId=org.apache.cxf.archetype \
    -DarchetypeArtifactId=cxf-jaxrs-service \ 
    -DinteractiveMode=false

### CXF Multiparts

[JAX-RS : Support for Multiparts ](http://cxf.apache.org/docs/jax-rs-multiparts.html)

### CXF Debugging Tools

[Debugging Tools](http://cxf.apache.org/docs/debugging-and-logging.html)

### Upload Files

    curl -X POST -F 'key1=value1' -F 'key2=value2' -F 'file1=@file1.txt' -F 'file2=@file2.txt' http://localhost:8080/my/downloads

[POST Form Data with cURL](https://davidwalsh.name/curl-post-file)