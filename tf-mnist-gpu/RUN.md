docker build -t gpu/tf-mnist:v1 .

Create following directories on the node on which tf gpu must run

/root/tf-mnist/mnist_data
/root/tf-mnist/mnist_model
/root/tf-mnist/trained_model

One can create these dirs in any path. In such case edit the tfjob-gpu.yaml file.

cp -r ./mnist_data /root/tf-mnist/mnist_data

kubectl create -f tfjob-gpu.yaml

Note: Change the "nodeSelector" field in tfjob-gpu.yaml to appropriate node in the setup.
