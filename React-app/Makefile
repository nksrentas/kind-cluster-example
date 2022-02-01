install_kind:
	curl --location  https://github.com/kubernetes-sigs/kind/releases/download/v0.11.1/kind-windows-amd64 --output kind

create_docker_registry:
	docker run -d -p 5000:5000 --restart=always --name registry registry:2

# 4
create_deployment:
	kubectl apply -f deployment.yaml

# 3
connect_registry_to_kind_network:
	docker network connect kind registry

# 2
apply_config_map:
	kubectl apply -f kind_configmap.yaml

# 1
create_cluster: 
	./kind create cluster --name hw-app --config kind_cluster.yaml

delete_cluster:
	./kind delete cluster --name hw-app

