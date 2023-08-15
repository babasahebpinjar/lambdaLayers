
To create AWS lambda layer https://medium.com/sopmac-labs/langchain-aws-lambda-serverless-q-a-chatbot-203470b9906f

Creating layers sing Sam(cloud9)

virtualenv v-env

source ./v-env/bin/activate

pip install boto3

pip install botocore

deactivate

mkdir botolib

cd botolib/

cp -r ../v-env/lib64/python3.7/site-packages/* .

cd ..

zip -r botolib.zip ./botolib

aws lambda publish-layer-version --layer-name botolayer --zip-file fileb://botolib.zip --compatible-runtimes python3.7
