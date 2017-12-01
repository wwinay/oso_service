# oso_service
create service and mount in container

# oc create -n myproject -f secrets.json

mention the service account in yaml file

also add the volume in yaml configuration

"volumes": [
             {
              "name": "php-volume",
              "secret": {
                    "secretName": "php-app-secret"
               }
             }
             
Mount the volume as below

Raw
 "containers": [
              {
                "name": "cakephp-example",
                "image": "cakephp-example",
                "volumeMounts": [
                  {
                     "name": "php-volume",
                     "mountPath": "/etc/php-secret-volume",
                     "readOnly": true
                   }
                 ],
                 
                 
The example yaml is attached for reference

start the deployment

NOTE : THE CERTIFICATE AND KEY NEEDS TO BE CONVERTED TO BASE64 using echo "cert" | base64 -w 0 command. Put the the certificate in data field in service.jason


                 
