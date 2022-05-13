# mesh-demo

```
CERTS=$(grep 'END CERTIFICATE' ca-bundle.crt | wc -l)
for N in $(seq 0 $(($CERTS - 1 ))); do ALIAS="ca-bundle-$N"; cat ca-bundle.crt | awk "n==$N {print}; /END CERTIFICATE/ { n++ }" | keytool -noprompt -import -trustcacerts -alias $ALIAS -keystore $JAVA_HOME/jre/lib/security/cacerts -storepass changeit; done
```

```
curl -O https://mirror.openshift.com/pub/openshift-v4/x86_64/clients/ocp/stable/openshift-client-linux.tar.gz
tar -xvzf openshift-client-linux.tar.gz 
sudo cp oc /usr/bin/
```
