version=11.0.21

create-multi-arch-builder:
	docker buildx create --name=dockerbuilder --driver docker-container --platform linux/amd64,linux/arm64
	
image-oracle-jdk-11:
	docker buildx build --builder dockerbuilder --platform linux/amd64,linux/arm64 -t hurdes/ubuntu-oracle-jdk:${version} -f ./Dockerfile --push .

push-oracle-jdk-11:
	docker push hurdes/ubuntu-oracle-jdk:${version}